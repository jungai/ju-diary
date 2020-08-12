<template>
  <div class="home">
    <Header />
    <nuxt />
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/Header'
import Footer from '@/components/Footer'

export default {
  components: {
    Header,
    Footer,
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

.home {
  margin: 0 auto;
  max-width: 960px;
  width: 100%;
  position: relative;
  height: 100vh;
}
</style>
