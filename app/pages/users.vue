<template>
    <div class="servers">
      <PageWrapper>
        <PageHeader title="Сервера" />
        <TablePage :data="data" :title="title" />
      </PageWrapper>
    </div>
  </template>
  
  <script lang="ts" setup>
  type Users = {
    id: number;
    username: string;
    department: string;
    computer_name: string;
    office: number;
  }
  const title = {
    title1: { accessKey: "id", header: "#" },
    title2: { accessKey: "username", header: "Имя пользователя" },
    title3: { accessKey: "department", header: "Отдел" },
    title4: { accessKey: "computer_name", header: "Компьютер" },
    title5: { accessKey: "office", header: "Кабинет" }
  }
  
  const data = ref<Users[]>([
    {
      id: 1,
      username: "test1",
      department: "Административно-управленческий",
      computer_name: 'Computer 1',
      office:52,
    },
    {
      id: 2,
      username: "test2",
      department: "Административно-управленческий",
      computer_name: 'Computer 2',
      office:50,
    },
  ])
  </script>