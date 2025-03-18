<script setup lang="ts">
defineProps<{
  title: string;
  description: string
}>()
</script>

<template>
  <div class="card">
    <div class="card-header">
      <h2>{{ title }}</h2>
    </div>
    <div class="body">
      <p>{{ description }}</p>
    </div>
  </div>
</template>

<style scoped>
.card {
  background-color: grey;
  border-radius: 7;
}

.card-header {
  height: 20%;
  color: white;
}

.card-body {
  color: green;
}
</style>