<script setup lang="ts">
  import gsap from 'gsap'

  import CardItem from './CardItem.vue'
  import AccordionItem from "./AccordionItem.vue"

  import cv from '../assets/Luke_Cheung.pdf'

  import * as contentObj from '../content'

  const contentArr = Object.values(contentObj)
  const onEnter = (el: Element, done: () => void) => {
    const index = parseInt((el as HTMLElement).dataset.index!)
    const delay = index < 11
      ? index * 0.1
      : 1 + (1 / index)

    gsap.from(el, {
      ease: 'back.out(0.6)',
      transform: 'translateY(1000%)',
      delay,
      onComplete: done
    })
  }

  const redirect = (link: string) => () => window.location.href = link
</script>

<template>
  <AccordionItem header-text="CV">
    <embed class="cv" :src="cv" type="application/pdf">
  </AccordionItem>
  <TransitionGroup
    appear
    tag="ul"
    class="body"
    @enter="onEnter"
  >
    <li
      v-for="(content, index) in contentArr"
      :key="content.title"
      :data-index="index"
      @click="redirect(content.link)"
    >
      <CardItem v-bind="content"/>
    </li>
  </TransitionGroup>
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
  list-style-type: none;
}

.cv {
  width: inherit;
  height: inherit;
}
</style>