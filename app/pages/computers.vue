<template>
  <div class="computers">
    <UContainer>
      <Wrapper>
        <div class="computers__header">

          <div class="sec">
            <div class="title">Компьютеры</div>
          </div>

          <div class="view sec">
            <UButton @click="editView()">Таблица</UButton>
            <UButton @click="editView()">Карточка</UButton>
          </div>

        </div>
        <Table :data = "computers" v-if="view === true"/>
        <CardList :data = "computers" v-else/>
      </Wrapper>
    </UContainer>
  </div>
</template>

<script lang="ts" setup>
const computers = [{
  id: 1,
  name: 'Computer 1',
  description: 'Work PC',
  office: 50,
  username: 'testuser',
  serialnumber: 12345612345
},
{
  id: 2,
  name: 'Computer 2',
  description: 'Work PC',
  office: 50,
  username: 'testuser',
  serialnumber: 12345612345
},
]
let view = ref(false)
const editView = ()=>{
  view.value =   !view.value
}
</script>

<style scoped>
.computers__header {
  display: grid;
  grid-template-columns: 1fr 1fr;
  margin-bottom: 40px;
}
.view {
  display: flex;
  gap: 20px;
  justify-content: flex-end;
}
</style>
