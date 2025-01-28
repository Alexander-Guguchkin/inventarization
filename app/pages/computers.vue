<template>
  <div class="computers">
    <PageWrapper>
      <PageHeader title="Компьютеры" />
      <TablePage :data="data" :title="title" />
    </PageWrapper>
  </div>
</template>
<script setup lang="ts">
const title = {
  title1: { accessKey: "id", header: "#" },
  title2: { accessKey: "name", header: "Имя компьютера" },
  title3: { accessKey: "status", header: "Статус" },
  title4: { accessKey: "office", header: "Кабинет" },
  title5: { accessKey: "username", header: "Имя пользователя" }
}
type Computers = {
  id: number;
  name: string;
  office: number;
  username: string;
  status: "работает" | "сломан" | "ремонт";
};

const data = ref<Computers[]>([
  {
    id: 1,
    name: "Computer 1",
    status: "сломан",
    office: 50,
    username: "testuser",
    serialnumber: 5790,
  },
  {
    id: 2,
    name: "Computer 2",
    status: "работает",
    office: 52,
    username: "testuser",
    serialnumber: 5490,
  },
]);

</script>
