<script setup lang="ts">
const items = ref([
  [
    {
      label: 'Профиль',
      avatar: {
        src: 'https://avatars.githubusercontent.com/u/739984?v=4'
      },
      to: '/profile'
    },
    {
      label: 'Главная',
      type: 'label',
      icon: 'i-lucide-house',
      to: '/'
    },
    {
      label: 'ПК и орг техника',
      icon: 'i-meteor-icons:devices',
      children: [
        {
          label: 'Компьютеры',
          description: 'Fully styled and customizable components for Nuxt.',
          icon: 'i-lucide-computer',
          to: '/computers'
        },
        {
          label: 'Комплектующие',
          description: 'Fully styled and customizable components for Nuxt.',
          icon: 'i-lucide-microchip',
          to: '/accessories'
        },

        {
          label: 'Мониторы',
          description: 'Learn how to install and configure Nuxt UI in your application.',
          icon: 'i-lucide:monitor',
          to: '/monitors'
        },
        {
          label: 'Перефирия',
          icon: 'i-lucide:keyboard',
          description: 'You have nothing to do, @nuxt/icon will handle it automatically.',
          to: '/periphery'
        },
        {
          label: 'Орг. техника',
          icon: 'i-lucide:printer',
          description: 'Choose a primary and a neutral color from your Tailwind CSS theme.',
          to: '/orgTech'
        }
      ]
    },
    {
      label: 'Сервера',
      icon: 'i-lucide-database',
      to: '/servers'
    },
    {
      label: 'Пароли',
      icon: 'i-lucide-lock-keyhole',
      to: '/passwords'
    },
    {
      label: 'Пользователи',
      icon: 'i-lucide-smile',
      to: '/users'
    },

  ],
  [
    {
      label: 'Настройки',
      icon: 'i-lucide-bolt',
    },
    {
      label: 'Помощь',
      icon: 'i-lucide-circle-help',
    }
  ]
])
</script>

<template>
  <div class="header">
    <UNavigationMenu orientation="vertical" :items="items" class="data-[orientation=vertical]:w-48" />
  </div>
</template>
<style scoped>
.header {
  background: rgb(48, 48, 48);
  height: 100vh;
  padding-top: 20px;
  display: flex;
  justify-content: center;
  width: 100%;
}
</style>
