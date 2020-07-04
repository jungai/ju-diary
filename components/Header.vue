<template>
  <header>
    <h1>{{ header }}</h1>
  </header>
</template>

<script>
import { defineComponent, ref } from 'nuxt-composition-api'

export default defineComponent({
  setup() {
    const header = ref('blog')

    return { header }
  },
})
</script>

<style>
header {
  padding: 0.8rem;
  display: flex;
  justify-content: center;
  background-image: repeating-linear-gradient(
    135deg,
    white 0px,
    white 20px,
    tomato 20px,
    tomato 40px
  );
  /* color: tomato; */
}
</style>
