<template>
  <div class="accessories">
    <PageWrapper>
      <PageHeader title="Комплеутующие" />
      <TableStatus :data="data" :title="title" />
    </PageWrapper>
  </div>
</template>

<script lang="ts" setup>
type Accessories = {
  id: number;
  name: string;
  description: string;
  computer_id: number;
  status: "работает" | "сломан" | "ремонт";
}
const title = {
  title1: { accessKey: "id", header: "#" },
  title2: { accessKey: "name", header: "Имя комплектующего" },
  title3: { accessKey: "status", header: "Статус" },
  title4: { accessKey: "description", header: "Описание" },
  title5: { accessKey: "computer_id", header: "Компьютер" }
}

const data = ref<Accessories[]>([
  {
    id: 1,
    name: "intel 1",
    status: "сломан",
    description: 'cpu',
    computer_id: 1,
  },
  {
    id: 2,
    name: "intel 2",
    status: "работает",
    description: 'cpu',
    computer_id: 2
  },
])
</script>