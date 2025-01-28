<template>
  <div class="computers__list">
    <UCard v-for="elem in props.data">
      <template #header>
        Имя компьютера: {{ elem.name }}
      </template>
      <div class="computers__info">
        <div class="description">Описание: {{ elem.description }}</div>
        <div class="office">Кабинет: {{ elem.office }}</div>
        <div class="username">Имя пользователя: {{ elem.username }}</div>
        <div class="serialnumber">Серийный номер: {{ elem.serialnumber }}</div>
      </div>
    </UCard>
  </div>
</template>

<script lang="ts" setup>
const props = defineProps<{
  data: object
}>()
</script>

<style>
.computers__list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.computers__info {
  display: flex;
  flex-direction: column;
  gap: 20px;
}
</style>