<template>
  <header>
    <div>
      <img src="../public/Logo.png" alt="Logo-Image">
    </div>

    <nav>
      <ul>
        <li><NuxtLink to="/pages/blog">Blogs</NuxtLink></li>
     </ul>
    </nav>
    <div>
      <div>   
        <li><NuxtLink to="login">Login</NuxtLink></li>
      </div>
    </div>
  </header>
</template>

<style scoped>
  img {
    height: 8vh;
    width: 27vh;
}
</style>