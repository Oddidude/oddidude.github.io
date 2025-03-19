<script setup lang="ts">
  import CardItem from './CardItem.vue';

  import * as contentArr from '../content'
</script>

<template>
  <div class="body">
    <div v-for="content in contentArr" :key="content.title">
      <CardItem v-bind="content" />
    </div>
  </div>
</template>

<style scoped>
.body {
  width: 100%;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  gap: 2%;
  margin-top: 1%;
  padding: 0 1%;
}
</style>