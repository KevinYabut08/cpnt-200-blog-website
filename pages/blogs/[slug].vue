<script setup>
const route = useRoute();
const { data: blogs } = await useFetch(`/pages/blogs/${route.params.slug}`);
</script>
<template>
  <main>
    <h1>{{ post.title }}</h1>
    <p>{{ post.content }}</p>

    <ul>
      <li v-for="(category, index) in post.categories" :key="index">
        {{ category }}
      </li>
    </ul>
  </main>
</template>
