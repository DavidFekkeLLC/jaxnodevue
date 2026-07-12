<script setup lang="ts">
const router = useRouter()

const nav = [
  { label: 'Home', to: '/' },
  { label: 'About', to: '/about' }
]
</script>

<template>
  <div>
    <nav>
      <ul>
        <li v-for="item in nav" :key="item.to">
          <NuxtLink :to="item.to">{{ item.label }}</NuxtLink>
        </li>
      </ul>
    </nav>
    <NuxtPage />
  </div>
</template>