<script setup>
const { data: posts } = await useFetch("/api/blog", {
  headers: useRequestHeaders(["cookie"]),
});
</script>
<template>
  <main>
    <h1>BLOGS</h1>
    <div>
      <h2>Batanes:The Untouched Beauty of the North</h2>
      <p>
        Tucked away in the northernmost part of the Philippines lies Batanes, a
        group of rugged islands renowned for their dramatic landscapes and rich
        Ivatan culture. Unlike any other destination in the country, Batanes
        boasts rolling hills, towering cliffs, and rich Ivatan culture. Unlike
        any other destination in the country, Batanes boasts rolling hills,
        towering cliffs, and traditional stone houses that transport visitors to
        a bygone era. Explore the picturesque towns of Basco and Sabtang, hike
        to secluded beaches, and immerse yourself in the warm hospitality of the
        locals for an authentic island experience unlike any other.
      </p>
    </div>
   
  </main>
  <div>
    <ul>
      <li v-for="(post, index) in posts" :key="index">
        <NuxtLink :to="`/blog/${post.slug}`">{{ post.title }}</NuxtLink>
      </li>
    </ul>
  </div>
  <button type="button"><NuxtLink to="landing-page">HOME</NuxtLink></button>

</template>
<style>
h1 {
  text-align: center;
  font-size: 50px;
}
h2 {
  text-align: center;
}
p {
  text-align: start;
  margin: 100px;
}
button {
    border-radius: 12px;
    background: #7fb0d7;
    border: none;
    height: 5vh;
    width: 12vh;
  }
</style>
