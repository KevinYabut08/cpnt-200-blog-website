<script setup>
import { ref } from 'vue';
const supabase = useSupabaseClient();
const user = useSupabaseUser();
const router = useRouter();
// if (user.value === null){
//   router.push('/error')
// }
const { data: blogs } = await useAsyncData("blogs", async () => {
  const { data } = await supabase.from("blogs").select("*");
  // data.map((blog) => {
  //   const slug = slugify(blog.title);
  //   blog.slug = slug;
  // });
  return data;

})

//DONE: Make blog post appear when the nuxtlink is clicked
const showBlog = ref(false);

//DONE: Create Function to make the blog popup
const openBlog = () => {
  showBlog.value = true;
};

//DONE: Create function to close the blog pop up

const closeBlog = () => {
  showBlog.value = false;
};
</script>
<template>
  
  <section>
    <ul>
      <li v-for="(blog, index) in blogs" :key="index">
        <NuxtLink :to="blog" @click="openBlog">{{ blog.title }}</NuxtLink>
       <div v-if="showBlog" class="popup">
        <div class="blog-content">
          <h2>{{ blog.title }}</h2>
          <p>{{ blog.description }}</p>

          <button @click="closeBlog">Close Blog</button>
        </div>
       </div>
        <!-- <NuxtLink @click="blogs(blog)"> {{ blog.title }}</NuxtLink> -->
       <!-- <div v-if="blogs(blog)">
          <h2>{{ blog.title }}</h2>
          <p>{{ blog.description }}</p>
       </div> -->
       <!-- <NuxtLink to=>{{ blog.title }}</NuxtLink> -->
      </li>
    </ul>
  </section>
</template>
<style scoped>
  button {
    cursor: pointer;
  }
</style>