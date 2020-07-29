<template>
  <CardList>
    <Card
      v-for="post in posts"
      :key="post.slug"
      :title="post.title"
      :go-to="post.slug"
      :description="post.description"
    />
  </CardList>
</template>

<script>
import { useAsync } from 'nuxt-composition-api'
import CardList from '@/components/CardList'
import Card from '@/components/Card'

export default {
  components: { CardList, Card },
  setup(_, ctx) {
    const posts = useAsync(async () => await ctx.root.$content('posts').fetch())
    return { posts }
  },
}
</script>

<style></style>
