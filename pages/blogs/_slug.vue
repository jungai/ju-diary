<template>
  <article>
    <h1>{{ doc[0].title }}</h1>
    <nuxt-content :document="doc[0]" />
  </article>
</template>

<script>
import { useAsync } from 'nuxt-composition-api'

export default {
  layout: 'blog',
  setup(_, ctx) {
    const slug = ctx.root.$route.params.slug

    const doc = useAsync(
      async () => await ctx.root.$content('posts').search('slug', slug).fetch()
    )
    return { doc }
  },
}
</script>

<style></style>
