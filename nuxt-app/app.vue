<template>
  <div>
    <h1>JSON data</h1>
    <pre>{{ jsonData }}</pre>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const jsonData = ref([])

onMounted(async () => {
  const res = await fetch('/data.json')
  jsonData.value = await res.json()
})
</script>
