<script setup>
const supabase = useSupabaseClient();
const user = useSupabaseUser();
const router = useRouter();
// if (user.value === null){
//   router.push('/error')
// }
const { data: blogs } = await useAsyncData("blogs", async () => {
  const { data } = await supabase.from("blogs").select("title");
  // data.map((blog) => {
  //   const slug = slugify(blog.title);
  //   blog.slug = slug;
  // });
  return data;
})
</script>
<template>
  
  <section>
    <ul>
      <li v-for="(blog, index) in blogs" :key="index">
       {{ blog.title }}
      </li>
    </ul>
  </section>
</template>
