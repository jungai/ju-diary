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
import CardList from '@/components/CardList'
import Card from '@/components/Card'

export default {
  components: { CardList, Card },
  async asyncData({ $content }) {
    const posts = await $content('posts').fetch()

    return { posts }
  },
}
</script>

<style></style>
