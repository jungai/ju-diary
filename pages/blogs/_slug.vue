<template>
  <article class="content">
    <h1>{{ doc[0].title }}</h1>
    <nuxt-content :document="doc[0]" />
  </article>
</template>

<script>
export default {
  layout: 'blog',
  async asyncData({ $content, route, error }) {
    const slug = route.params.slug

    const doc = await $content('posts').search('slug', slug).fetch()

    if (doc.length === 0) {
      error({ statusCode: 404, message: 'Post not found' })
    }

    return { doc }
  },
  head() {
    return {
      title: this.doc[0].title,
    }
  },
}
</script>

<style lang="scss">
@import '~/assets/css/mixins/media.scss';

.content {
  padding: 1em;

  > h1 {
    text-align: center;
    font-size: 2em;
    margin-bottom: 0.8em;
    border-bottom: tomato 4px solid;

    @include for-phone-only {
      font-size: 1.4em;
    }
  }

  .nuxt-content * {
    font-size: 1.2em;
    margin: 0.5em 0;

    @include for-phone-only {
      font-size: 0.9em;
    }
  }

  .nuxt-content h3 {
    background-color: tomato;
    // background-color: #40739e;
    color: white;
    display: inline-block;
    padding: 0 0.3em 0 1em;
  }
}
</style>
