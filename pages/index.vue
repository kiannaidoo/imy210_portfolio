<!-- Kian Naidoo - u25618670 -->
<template>
  <div class="container">
    <h1>Kian Naidoo</h1>
    <img src="/profile.jpeg" width="150" alt="Profile photo" />
    <p>
      I am a web development student passionate about building modern
      websites using Jamstack technologies.
    </p>

    <div class="fact-box">
      <strong>🐱 Random Cat Fact:</strong>
      <p>{{ fact || 'Loading fact...' }}</p>
    </div>

    <Weather />
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import Weather from '~/components/Weather.vue'

const fact = ref('')

onMounted(async () => {
  try {
    const res = await fetch('https://catfact.ninja/fact')
    const data = await res.json()
    fact.value = data.fact
  } catch (e) {
    fact.value = 'Could not load fact.'
  }
})
</script>