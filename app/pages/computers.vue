<template>
  <div class="computers">

    <PageWrapper>
      <PageHeader title="Компьютеры" />
      <div class="flex flex-col flex-1 w-full">
        <div class="flex px-4 py-3.5 border-b border-[var(--ui-border-accented)]">
          <UInput v-model="globalFilter" class="max-w-sm" placeholder="Filter..." />
        </div>

        <UTable ref="table" v-model:global-filter="globalFilter" :data="data" :columns="columns" />
      </div>
    </PageWrapper>

  </div>

</template>



<script setup lang="ts">
import { h, resolveComponent } from "vue";
import type { TableColumn } from "@nuxt/ui";

const UBadge = resolveComponent("UBadge");
type Computers = {
  id: string;
  name: string;
  office: number;
  username: string;
  status: "работает" | "сломан" | "ремонт";
  serialnumber: number;
};

const data = ref<Computers[]>([
  {
    id: "1",
    name: "Computer 1",
    status: "сломан",
    office: 50,
    username: "testuser",
    serialnumber: 1,
  },
  {
    id: "2",
    name: "Computer 2",
    status: "работает",
    office: 50,
    username: "testuser",
    serialnumber: 2,
  },
]);

const columns: TableColumn<Computers>[] = [
  {
    accessorKey: "id",
    header: () => h("div", { class: "text-center" }, "#"),
    cell: ({ row }) => {
      return h("div", { class: "text-center font-medium" }, `#${row.getValue("id")}`);
    },
  },
  {
    accessorKey: "name",
    header: () => h("div", { class: "text-center" }, "Имя компьютера"),
    cell: ({ row }) => {
      return h("div", { class: "text-center font-medium" }, row.getValue("name"));
    },
  },
  {
    accessorKey: "status",
    header: () => h("div", { class: "text-center" }, "Статус"),
    cell: ({ row }) => {
      const color = {
        работает: "success" as const,
        сломан: "error" as const,
        ремонт: "neutral" as const,
      }[row.getValue("status") as string];

      return h(
        "div",
        { class: "text-center" },
        h(UBadge, { class: "capitalize", variant: "subtle", color }, () =>
          row.getValue("status")
        ))
    },
  },
  {
    accessorKey: "username",
    header: () => h("div", { class: "text-center" }, "Имя пользователя"),
    cell: ({ row }) => {
      return h("div", { class: "text-center font-medium" }, row.getValue("username"));
    },
  },
  {
    accessorKey: "serialnumber",
    header: () => h("div", { class: "text-center" }, "Серийный номер"),
    cell: ({ row }) => {
      return h("div", { class: "text-center font-medium" }, row.getValue("serialnumber"));
    },
  },
];

const table = useTemplateRef("table");

const globalFilter = ref();
</script>
<style scoped>
.page__header {
  margin-bottom: 40px;
}

.text-center {
  text-align: center;
}
</style>