<template>
  <div>
    <div class="flex flex-col flex-1 w-full">
      <div class="flex px-4 py-3.5 border-b border-[var(--ui-border-accented)]">
        <UInput v-model="globalFilter" class="max-w-sm mx-6" placeholder="Filter..." />
        <UButton icon="i-lucide-plus" class="cursor-pointer" />
      </div>
      <UTable ref="table" v-model:global-filter="globalFilter" :data="data" :columns="columns" />
    </div>
  </div>
</template>
<script setup lang="ts">
import { h, resolveComponent } from "vue";
import type { TableColumn } from "@nuxt/ui";
const props = defineProps<{
  data: object,
  title: object,
}>()
const UBadge = resolveComponent("UBadge");

const columns: TableColumn[] = [
  {
    accessorKey: props.title.title1.accessKey,
    header: () => h("div", { class: "text-center" }, props.title.title1.header),
    cell: ({ row }) => {
      return h("div", { class: "text-center font-medium" }, `#${row.getValue(props.title.title1.accessKey)}`);
    },
  },
  {
    accessorKey: props.title.title2.accessKey,
    header: () => h("div", { class: "text-center" }, props.title.title2.header),
    cell: ({ row }) => {
      return h("div", { class: "text-center font-medium" }, row.getValue(props.title.title2.accessKey));
    },
  },
  {
    accessorKey: props.title.title3.accessKey,
    header: () => h("div", { class: "text-center" }, props.title.title3.header),
    cell: ({ row }) => {
      return h("div", { class: "text-center" }, row.getValue(props.title.title3.accessKey))
    },
  },
  {
    accessorKey: props.title.title4.accessKey,
    header: () => h("div", { class: "text-center" }, props.title.title4.header),
    cell: ({ row }) => {
      return h("div", { class: "text-center font-medium" }, row.getValue(props.title.title4.accessKey));
    },
  },
  {
    accessorKey: props.title.title5.accessKey,
    header: () => h("div", { class: "text-center" }, props.title.title5.header),
    cell: ({ row }) => {
      return h("div", { class: "text-center font-medium" }, row.getValue(props.title.title5.accessKey));
    },
  },
];

const table = useTemplateRef("table");

const globalFilter = ref(); // поменять глобальны фильтр на id и название 
</script>