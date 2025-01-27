<script setup lang="ts">
const items = ref([
  [
    {
      label:'Профиль',
      avatar: {
        src: 'https://avatars.githubusercontent.com/u/739984?v=4'
      },
      badge: 100
    },
    {
      label: 'Главная',
      type: 'label',
      icon:'i-lucide-house',
      to:'/'
    },
    {
      label: 'ПК и орг техника',
      icon: 'i-lucide-book-open',
      children: [
      {
          label: 'Компьютеры',
          description: 'Fully styled and customizable components for Nuxt.',
          icon: 'i-lucide-house',
          to:'/computers'
        },
        {
          label: 'Комплектующие',
          description: 'Fully styled and customizable components for Nuxt.',
          icon: 'i-lucide-house',
        },

        {
          label: 'Мониторы',
          description: 'Learn how to install and configure Nuxt UI in your application.',
          icon: 'i-lucide-cloud-download'
        },
        {
          label: 'Гарнитура',
          icon: 'i-lucide-smile',
          description: 'You have nothing to do, @nuxt/icon will handle it automatically.'
        },
        {
          label: 'Орг. техника',
          icon: 'i-lucide-swatch-book',
          description: 'Choose a primary and a neutral color from your Tailwind CSS theme.'
        }
      ]
    },
    {
      label: 'Сервера',
      icon: 'i-lucide-database',
      to:'/servers'
    },
    {
      label: 'Пароли',
      icon: 'i-lucide-box',
      to:'/password'
    },
    {
      label: 'Прочее',
      icon: 'i-lucide-box',
      to:'/password'
    },
    {
      label: 'Пользователи',
      icon: 'i-lucide-box',
      to:'/password'
    },
    
  ],
  [
    {
      label: 'Настройки',
      icon: 'i-simple-icons-github',
    },
    {
      label: 'Help',
      icon: 'i-lucide-circle-help',
    }
  ]
])
</script>

<template>
  <div class="header">
    <UContainer>
      <UNavigationMenu orientation="vertical" :items="items" class="data-[orientation=vertical]:w-48" />
    </UContainer>
  </div>
</template>
<style scoped>
.header {
  background: rgb(48, 48, 48);
  height: 100vh;
  padding-top: 20px;
}
</style>
