<template>
  <div class="error">
    <img
      src="https://media3.giphy.com/media/l3fZBHqfuBw1mmDGE/giphy.gif"
      alt="Okay IU"
      width="400"
    />
    <p v-if="error.statusCode === 404">ไม่มีหน้านี้</p>
    <h1 v-else>เกิดปัญหาบางอย่าง</h1>
    <nuxt-link to="/">กลับไปหน้าแรก</nuxt-link>
  </div>
</template>

<script>
export default {
  props: {
    error: {
      type: Object,
      default: null,
    },
  },
  layout: 'center', // you can set a custom layout for the error page
}
</script>

<style scoped lang="scss">
.error {
  display: flex;
  align-items: center;
  flex-direction: column;
  font-size: 1.2em;
}
</style>
