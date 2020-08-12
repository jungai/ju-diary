<template>
  <article>
    <h1>{{ doc[0].title }}</h1>
    <nuxt-content :document="doc[0]" />
  </article>
</template>

<script>
export default {
  layout: 'blog',
  async asyncData({ $content, route }) {
    const slug = route.params.slug

    const doc = await $content('posts').search('slug', slug).fetch()

    return { doc }
  },
}
</script>

<style></style>
