<template>
    <div class="periphery">
        <PageWrapper>
            <PageHeader title="Перефирия" />
            <TableStatus :data="data" :title="title" />
        </PageWrapper>
    </div>
</template>
<script lang="ts" setup>
type Periphery = {
    id: number,
    name: string,
    office: number,
    computer_id: number,
    status: "работает" | "сломан" | "ремонт";
}
const data = ref<Periphery[]>([
    {
        id: 1,
        name: 'Клавиатура',
        office: 20,
        computer_id: 1,
        status: "сломан"
    }
])
const title = {
  title1: { accessKey: "id", header: "#" },
  title2: { accessKey: "name", header: "Имя устройства" },
  title3: { accessKey: "status", header: "Статус" },
  title4: { accessKey: "office", header: "Кабинет" },
  title5: { accessKey: "computer_id", header: "Компьютер" }
}
</script>
