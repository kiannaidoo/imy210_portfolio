<!-- Kian Naidoo - u25618670 -->
<template>
  <div class="weather-box">
    <h2>🌤 Current Weather (Pretoria)</h2>
    <p v-if="weather">Temperature: {{ weather }}°C</p>
    <p v-else>Loading weather...</p>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const weather = ref(null)

onMounted(async () => {
  try {
    const res = await fetch(
      'https://api.open-meteo.com/v1/forecast?latitude=-25.7479&longitude=28.2293&current_weather=true'
    )
    const data = await res.json()
    weather.value = data.current_weather.temperature
  } catch (e) {
    weather.value = 'unavailable'
  }
})
</script>