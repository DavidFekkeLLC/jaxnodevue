<script setup>
import { ref } from 'vue';

const name = ref('JaxNode');
</script>
<template>

    <section id="center">
    
        <div>
        <h1>Hello, {{ name }}!</h1>
        <p>Edit <code>src/components/JaxNodeHelloWorld.vue</code> and save to test <code>HMR</code></p>
        </div>

    </section>

  
</template>