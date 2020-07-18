<template>
  <div class="card">
    <h1 class="title">{{ title }}</h1>
    <span class="spacing" />
    <p>{{ description }}</p>
    <a class="read-more">อ่านต่อ..</a>
  </div>
</template>

<script>
import {} from 'nuxt-composition-api'

export default {
  name: 'Card',
  props: {
    title: {
      type: String,
      default: '',
    },
    tag: {
      type: String,
      default: 'code',
    },
    description: {
      type: String,
      default: '',
    },
  },
  setup() {
    return {}
  },
}
</script>

<style lang="scss" scoped>
@import '~/assets/css/mixins/media.scss';

.card {
  position: relative;
  border: 1px solid #dfe6e9;
  max-width: 650px;
  width: 100%;
  height: 200px;
  margin: 0.8rem;
  padding: 0.8rem;
  display: flex;
  flex-direction: column;

  > .title {
    font-size: 1.2rem;

    @include for-desktop-up {
      font-size: 1.7rem;
    }
  }

  > .spacing {
    margin-bottom: 0.5rem;
  }

  > .description {
    font-size: 0.8rem;
  }

  > .read-more {
    position: absolute;
    right: 0;
    bottom: 0;
    color: red;
    cursor: pointer;
    margin: 0.4rem;
  }

  > .read-more:hover {
    font-style: italic;
    color: gray;
  }
}
</style>
