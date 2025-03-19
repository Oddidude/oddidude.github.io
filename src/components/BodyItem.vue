<script setup lang="ts">
  import CardItem from './CardItem.vue';

  import * as contentArr from '../content'
  import gsap from 'gsap';

  const onEnter = (el: Element, done: () => void) => {
    gsap.from(el, {
      ease: 'back.out(0.6)',
      transform: 'translateY(1000%)',
      delay: parseInt((el as HTMLElement).dataset.index!) * 0.1,
      onComplete: done
    })
  }

  const redirect = (link: string) => () => window.location.href = link
</script>

<template>
    <TransitionGroup
      appear
      tag="ul"
      :css="false"
      class="body"
      @enter="onEnter"
    >
      <li
        v-for="(content, index) in Object.values(contentArr)"
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
</style>