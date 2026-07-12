<script setup>
import { ref, computed } from 'vue';
import HelloWorld from './components/HelloWorld.vue'
import JaxNodeHelloWorld from './components/JaxNodeHelloWorld.vue'
import Weather from './components/Weather.vue'
</script>

<template>
  <JaxNodeHelloWorld />
  <Weather />
</template>
