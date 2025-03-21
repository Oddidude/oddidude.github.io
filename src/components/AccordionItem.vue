<script setup lang="ts">
  import { ref } from 'vue'

  const { headerText } = defineProps<{
    headerText: string;
  }>()

  const isOpen = ref(false)

  const toggleAccordion = () => {
    isOpen.value = !isOpen.value
  }
</script>

<template>
  <div class="accordion">
    <button class="accordion-button" @click="toggleAccordion">
      <h2>
        {{ headerText }}
      </h2>
      <img v-bind:class="{ 'accordion-arrow': true, open: isOpen }" src="../icons/accordionArrow.svg">
    </button>
    <div v-bind:class="{ content: true, open: isOpen }">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.accordion {
  width: 10%;
  height: fit-content;
  margin-top: .5rem;
}

.accordion-button {
  color: var(--main-light-green);
  width: 100%;
  height: 3rem;
  background-color: grey;
  display: flex;
  justify-content: center;
  align-items: center;
  border: none;
  border-radius: 8px;
  padding: 0 1rem;
}

.accordion-arrow {
  margin-left: auto;
  width: auto;
  height: 1rem;
  transform: rotate(180deg);
  transition: transform .5s ease-out;
}

.accordion-arrow.open {
  transform: rotate(0deg);
  transition: transform .5s ease-out;
}

.content {
  width: 99vw;
  overflow: hidden;
  max-height: 0;
  transition: max-height .3s ease-out;
  height: 1000px;
}

.content.open {
  max-height: 1000px;
  transition: max-height .3s ease-out;
}


</style>