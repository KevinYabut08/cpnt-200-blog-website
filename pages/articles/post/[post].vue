<script>
  export default {
    async fetch() {
      const blogsId = this.$route.params.id
      this.blogs = await this.$supabase.from('blogs').select('*').eq('id', blogsId).single()
    },
    data() {
      return {
        post: {}
      }
    }
  }
</script>
<template>
  <main>
    <h1>{{ post.title }}</h1>
    <p>{{ post.content }}</p>
    <p>Post Updated: {{ post.date_updated }}</p>
  </main>
</template>
<style>
main {
  max-width: 800px;
  margin: 0 auto;
}
</style>
