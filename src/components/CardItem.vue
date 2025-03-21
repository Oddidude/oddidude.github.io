<script setup lang="ts">
defineProps<{
  title: string;
  description: string;
  link: string;
}>()
</script>

<template>
  <div class="card">
    <div class="card-header">
      <h2>{{ title }}</h2>
    </div>
    <div class="card-body">
      <p>{{ description }}</p>
    </div>
  </div>
</template>

<style scoped>
.card {
  background-color: grey;
  border-radius: 6px;
  padding: 4px 8px;
  width: 17rem;
  overflow-x: hidden;
  height: 100%;
  min-height: 16rem;
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: center;
  transition: transform 0.2s;
}

.card:hover{
  cursor: pointer;
  transform: scale(1.05);
  box-shadow: 2px 2px 5px var(--shadow), -2px -2px 5px var(--shadow);
  transition: transform 0.4s;
}

.card-header {
  color: var(--main-light-green);
}

.card-body {
  color: white;
  text-overflow: ellipsis;
  text-align: center;
}
</style>