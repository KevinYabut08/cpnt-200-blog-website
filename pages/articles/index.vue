<script setup>
const supabase = useSupabaseClient();
const { data: articles } = await useAsyncData("title", async() => {
  const { data } = await supabase.from("blog").select("title");
  data.map((article) => {
    const slug = slugify(article.title);
    article.slug = slug;
  });
  return data;
})
</script>
<template>
  <div>
      <h2>Siargao:Beyond the Surfing Mecca</h2>
      <p>
        While Siargao has gained fame as a surfing mecca, there's much more to
        this tropical paradise than its legendary waves. Venture beyond the surf
        breaks to discover hidden lagoons, secret waterfalls, and pristine
        mangrove forests teeming with wildlife. Explore the laid-back villages
        of General Luna and Pacifico, sample fresh seafood delicacies, and
        embark on island-hopping adventures to deserted islets for a true taste
        of island life in the Philippines.
      </p>
    </div>
    <div>
      <h2>Siquijor: The Mystical Island of Healing</h2>
      <p>
        Known as the "Island of Fire," Siquijor has long been shrouded in
        mystery and intrigue. Beyond its reputation for mysticism and folk
        healing, Siquijor boasts pristine beaches, enchanting waterfalls, and
        lush inland forests waiting to be explored. Discover hidden caves, swim
        in crystal-clear springs, and wander through centuries-old balete trees
        while immersing yourself in the island's mystical charm and natural
        beauty.
      </p>
    </div>
    <div>
      <h2>Dumaguete: Gateway to Adventure in Negros Oriental</h2>
      <p>
        Nestled on the southern coast of Negros Oriental, Dumaguete serves as a
        gateway to some of the region's most underrated treasures. Explore the
        underwater wonders of Apo Island, where vibrant coral reefs and diverse
        marine life await snorkelers and divers alike. Trek to the breathtaking
        Casaroro Falls, traverse the otherworldly landscapes of the Balinsasayao
        Twin Lakes, and sample the region's delectable cuisine for a taste of
        authentic Filipino hospitality.
      </p>
      </div>
      <section>
        <ul>
          <li v-for="(article, index) in articles" :key="index">
          <NuxtLink :to="`/articles/post/$article.slug`"> {{ article.title }}</NuxtLink>
          </li>
        </ul>
      </section>
</template>