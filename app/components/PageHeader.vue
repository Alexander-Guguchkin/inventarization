<template>
  <div class="page__header">
    <div class="title">{{props.title}}</div>
  </div>
</template>
<script setup lang="ts">
const props = defineProps<{
    title:string
}>();
</script>
<style scoped>
.page__header{
  margin-bottom: 40px;
}
</style>