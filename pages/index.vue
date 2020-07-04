<template>
  <main class="container">
    <div class="pages">
      <nuxt-link
        v-for="(post, index) in posts"
        :key="`${index}${post.title}`"
        :to="post.slug"
        class="box"
      >
        <h2>{{ post.title }}</h2>
        <p>{{ post.description }}</p>
      </nuxt-link>
    </div>
  </main>
</template>

<script>
import { useAsync } from 'nuxt-composition-api'

export default {
  setup(_, ctx) {
    const posts = useAsync(async () => await ctx.root.$content('posts').fetch())

    return { posts }
  },
}
</script>

<style scoped>
main {
  display: flex;
  padding: 2.5em;
  justify-content: center;
  align-items: center;
}

aside {
  width: 500px;
  align-self: start;
  padding: 1em;
  margin-right: 1em;
  border: 1px solid lightgrey;
}

.pages {
  max-width: 1024px;
  display: flex;
}

.nuxt-link {
  width: 500px;
  margin: 20px;
  background-color: tomato;
  display: flex;
  flex-direction: column;
}
</style>
