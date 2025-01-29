<template>
    <div class="servers">
      <PageWrapper>
        <PageHeader title="Сервера" />
        <TableStatus :data="data" :title="title" />
      </PageWrapper>
    </div>
  </template>
  
  <script lang="ts" setup>
  type Accessories = {
    id: number;
    name: string;
    description: string;
    os: string;
    status: "работает" | "сломан" | "ремонт";
  }
  const title = {
    title1: { accessKey: "id", header: "#" },
    title2: { accessKey: "name", header: "Имя сервера" },
    title3: { accessKey: "status", header: "Статус" },
    title4: { accessKey: "description", header: "Описание" },
    title5: { accessKey: "os", header: "Операционная система" }
  }
  
  const data = ref<Accessories[]>([
    {
      id: 1,
      name: "intel xeon 1",
      status: "сломан",
      description: 'Контроллер домена',
      os:'windows server 2019',
    },
    {
      id: 2,
      name: "intel xeon 2",
      status: "работает",
      description: 'Система виртулизации + контроллер домена red adm',
      os:'red virtualization',
    },
  ])
  </script>