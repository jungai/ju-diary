<template>
  <div class="card-list">
    <slot />
  </div>
</template>

<script>
export default {
  name: 'CardList',
}
</script>

<style lang="scss" scoped>
.card-list {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  max-width: 960px;
  width: 100%;
  margin: 0 auto;
  padding: 0.8rem;
}
</style>
