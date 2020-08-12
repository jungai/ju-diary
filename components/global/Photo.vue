<template>
  <div id="img-wrapper">
    <img class="img" :src="src" :alt="alt" />
  </div>
</template>

<script>
export default {
  props: {
    src: {
      type: String,
      required: true,
    },
    alt: {
      type: String,
      required: true,
    },
  },
}
</script>

<style scoped>
#img-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 1.2em;
}

.img {
  width: 80%;
}
</style>
