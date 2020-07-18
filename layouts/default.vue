<template>
  <div class="home">
    <Header />
    <nuxt />
  </div>
</template>

<script>
import Header from '@/components/Header'

export default {
  components: {
    Header,
  },
}
</script>

<style>
html {
  font-family: 'Lato', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
</style>
