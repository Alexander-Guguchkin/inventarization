<script setup lang="ts">
import { h, resolveComponent } from 'vue'
import { upperFirst } from 'scule'
import type { TableColumn } from '@nuxt/ui'

const props = defineProps<{
  data:object
}>()

const UButton = resolveComponent('UButton')
const UCheckbox = resolveComponent('UCheckbox')
const UBadge = resolveComponent('UBadge')
const UDropdownMenu = resolveComponent('UDropdownMenu')

const toast = useToast()

type Payment = {
  id: string
  name: string
  description: string
  office: number
  username: string
  serialnumber: number
}

const data = ref<Payment[]>(props.data)

const columns: TableColumn<Payment>[] = [{
  id: 'select',
  header: ({ table }) => h(UCheckbox, {
    'modelValue': table.getIsSomePageRowsSelected() ? 'indeterminate' : table.getIsAllPageRowsSelected(),
    'onUpdate:modelValue': (value: boolean | 'indeterminate') => table.toggleAllPageRowsSelected(!!value),
    'ariaLabel': 'Select all'
  }),
  cell: ({ row }) => h(UCheckbox, {
    'modelValue': row.getIsSelected(),
    'onUpdate:modelValue': (value: boolean | 'indeterminate') => row.toggleSelected(!!value),
    'ariaLabel': 'Select row'
  }),
  enableSorting: false,
  enableHiding: false
}, {
  accessorKey: 'id',
  header: '#',
  cell: ({ row }) => `#${row.getValue('id')}`
}, {
  accessorKey: 'name',
  header: 'Имя компьютера',
}, {
  accessorKey: 'description',
  header: 'Описание',
}, {
  accessorKey: 'office',
  header: 'Каабинет'
}, {
  accessorKey: 'username',
  header:'Имя пользователя',
  
},
{
  accessorKey: 'description',
  header:'Описание'
},
{
  id: 'actions',
  enableHiding: false,
  cell: ({ row }) => {
    const items = [{
      type: 'label',
      label: 'Действия'
    }, {
      label: 'Скопировать id компьютера',
      onSelect() {
        navigator.clipboard.writeText(row.original.id)

        toast.add({
          title: 'Идентификатор компьютера скопирован в буфер обмена!',
          color: 'success',
          icon: 'i-lucide-circle-check'
        })
      }
    }, {
      label: row.getIsExpanded() ? 'Скрыть' : 'Развернуть',
      onSelect() {
        row.toggleExpanded()
      }
    }, {
      type: 'separator'
    }, {
      label: 'Просмотр компьютера'
    }, {
      label: 'Удалить'
    }]

    return h('div', { class: 'text-right' }, h(UDropdownMenu, {
      content: {
        align: 'end'
      },
      items
    }, () => h(UButton, {
      icon: 'i-lucide-ellipsis-vertical',
      color: 'neutral',
      variant: 'ghost',
      class: 'ml-auto'
    })))
  }
}]

const table = useTemplateRef('table')

function randomize() {
  data.value = [...data.value].sort(() => Math.random() - 0.5)
}
</script>

<template>
  <div class="flex-1 divide-y divide-[var(--ui-border-accented)] w-full">
    <div class="flex items-center gap-2 px-4 py-3.5 overflow-x-auto">
      <UInput
        :model-value="(table?.tableApi?.getColumn('email')?.getFilterValue() as string)"
        class="max-w-sm min-w-[12ch]"
        placeholder="Filter emails..."
        @update:model-value="table?.tableApi?.getColumn('email')?.setFilterValue($event)"
      />

      <UButton color="neutral" label="Randomize" @click="randomize" />

      <UDropdownMenu
        :items="table?.tableApi?.getAllColumns().filter(column => column.getCanHide()).map(column => ({
          label: upperFirst(column.id),
          type: 'checkbox' as const,
          checked: column.getIsVisible(),
          onUpdateChecked(checked: boolean) {
            table?.tableApi?.getColumn(column.id)?.toggleVisibility(!!checked)
          },
          onSelect(e?: Event) {
            e?.preventDefault()
          }
        }))"
        :content="{ align: 'end' }"
      >
        <UButton
          label="Columns"
          color="neutral"
          variant="outline"
          trailing-icon="i-lucide-chevron-down"
          class="ml-auto"
        />
      </UDropdownMenu>
    </div>

    <UTable
      ref="table"
      :data="data"
      :columns="columns"
      sticky
      class="h-96"
    >
      <template #expanded="{ row }">
        <pre>{{ row.original }}</pre>
      </template>
    </UTable>

    <div class="px-4 py-3.5 text-sm text-[var(--ui-text-muted)]">
      {{ table?.tableApi?.getFilteredSelectedRowModel().rows.length || 0 }} of
      {{ table?.tableApi?.getFilteredRowModel().rows.length || 0 }} row(s) selected.
    </div>
  </div>
</template>