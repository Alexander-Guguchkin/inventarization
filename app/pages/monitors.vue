<template>
    <div class="monitors">
        <PageWrapper>
            <PageHeader title="Мониторы" />
            <TableStatus :data="data" :title="title" />
        </PageWrapper>
    </div>
</template>
<script lang="ts" setup>

const title = {
  title1: { accessKey: "id", header: "#" },
  title2: { accessKey: "name", header: "Имя комплектующего" },
  title3: { accessKey: "status", header: "Статус" },
  title4: { accessKey: "office", header: "Кабинет" },
  title5: { accessKey: "computer_id", header: "Компьютер" }
}


    type Monitors = {
        id: number,
        name: string,
        office: number,
        computer_id: number,
        status: "работает" | "сломан" | "ремонт";
    }
    const data = ref<Monitors[]>([
        {
            id: 1,
            name: 'LOC',
            office: 20,
            computer_id: 1,
            status: "ремонт"
        }
    ]);

  
</script>
