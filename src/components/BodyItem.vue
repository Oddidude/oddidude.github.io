<script setup lang="ts">
  import CardItem from './CardItem.vue';

  import PhysicsEngine from '../content/PhysicsEngine.json'
  import SnakeNEAT from '../content/SnakeNEAT.json'

  import { type Content } from '../types'
  
  const contentArr: Content[] = [
    PhysicsEngine,
    SnakeNEAT
  ]
</script>

<template>
  <div v-for="content in contentArr" :key="content.title">
    <CardItem v-bind="content" />
  </div>
</template>