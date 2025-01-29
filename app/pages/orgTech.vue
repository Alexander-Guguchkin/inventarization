<template>
    <div class="orgTech">
        <PageWrapper>
            <PageHeader title="Орг. техника" />
            <TableStatus :data="data" :title="title" />
        </PageWrapper>
    </div>
</template>
<script lang="ts" setup>

const title = {
  title1: { accessKey: "id", header: "#" },
  title2: { accessKey: "name", header: "Имя устройства" },
  title3: { accessKey: "status", header: "Статус" },
  title4: { accessKey: "office", header: "Кабинет" },
  title5: { accessKey: "type", header: "Тип" }
}

  type orgTech = {
    id: number;
    name: string;
    office: number;
    type: "МФУ" | "принтер" | "сканер";
    status: "работает" | "сломан" | "ремонт";
  };
  const data = ref<orgTech[]>([
    {
      id: 1,
      name: "Kyocera Ecosys M2040dn",
      office: 20,
      type: "МФУ",
      status: "ремонт",
    },
  ]);


</script>
