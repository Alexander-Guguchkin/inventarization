<template>
    <div class="servers">
      <PageWrapper>
        <PageHeader title="Сервера" />
        <TablePage :data="data" :title="title" />
      </PageWrapper>
    </div>
  </template>
  
  <script lang="ts" setup>
  type Accessories = {
    id: number;
    login: string;
    description: string;
    password: string;
    link:string;
  }
  const title = {
    title1: { accessKey: "id", header: "#" },
    title2: { accessKey: "login", header: "Логин" },
    title3: { accessKey: "password", header: "Пароль" },
    title4: { accessKey: "description", header: "Описание" },
    title5: { accessKey: "link", header: "Ссылка на ресурс" }
  }
  
  const data = ref<Accessories[]>([
    {
      id: 1,
      login: "TEST2@mail.ru",
      description: "Почта 1",
      password: 'TEST1',
      link:'https://mail.ru',
    },
    {
      id: 2,
      login: "TEST2@mail.ru",
      description: "Почта 2",
      password: ' TEST12',
      link:'https://mail.ru',
    },
  ])
  </script>