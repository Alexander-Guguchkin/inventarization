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