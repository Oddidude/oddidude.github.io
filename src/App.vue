<script setup lang="ts">
import HeaderItem from "./components/HeaderItem.vue";
import BodyItem from "./components/BodyItem.vue";

import './styles/colours.css'
</script>

<template>
  <HeaderItem />
  <BodyItem />
</template>

<style>
:root {
  background-color: var(--background-dark-grey);
}
</style>