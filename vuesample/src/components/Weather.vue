<script setup>
import { onMounted,ref } from 'vue'

const airportIdentifier = ref('KCRG');
const metarURL = 'https://avwx.fekke.com/metar/';

const metarData = ref([]);

const fetchMetarData = async () => {
  metarData.value = [];
  try {
    const response = await fetch(`${metarURL}${airportIdentifier.value}`);
    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }
    const data = await response.json();
    metarData.value = [...data]; // Store the data in an array
  } catch (error) {
    console.error('Error fetching METAR data:', error);
  }
};

onMounted(() => {
  fetchMetarData();
});

</script>

<template>
  <section id="center">
    <div>
        <input v-model="airportIdentifier" placeholder="Enter Airport Identifier" />
        <button @click="fetchMetarData">Fetch Weather</button>
    </div>
    <div v-if="metarData.length > 0">
      <h1>Weather for {{ airportIdentifier }}</h1>
      <ul>
        <li v-for="(item, index) in metarData" :key="index">
          {{ item.raw_text }}
        </li>
      </ul>
    </div>
    <div v-else>
      <h1>Loading weather data...</h1>
    </div>
  </section>
</template>
