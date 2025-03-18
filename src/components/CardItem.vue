<script setup lang="ts">
const { link } = defineProps<{
  title: string;
  description: string;
  link: string;
}>()

const redirect = () => window.location.href = link
</script>

<template>
  <div class="card" @click="redirect">
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
  width: 15rem;
  overflow-x: hidden;
  height: 100%;
  min-height: 15rem;
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: center;
}

.card:hover{
  cursor: pointer;
  transform: scale(1.02);
  box-shadow: 2px 2px 5px var(--shadow), -2px -2px 5px var(--shadow);
  transition: all 0.2s;
}

.card-header {
  color: var(--main-light-green);
}

.card-body {
  color: white;
  text-overflow: ellipsis;
}
</style>