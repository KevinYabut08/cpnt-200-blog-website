<template>
  <div id="logo">
    <img src="../public//Logo.png" alt="logo-travel-blog" />
  </div>
  <div id="info">
    <img src="../public//Logo.png" alt="logo-travel-blog" />
  </div>
  <div>
    <button><a href="./blogs.vue">BLOGS!</a></button>
  </div>
</template>

<style scoped>
#l-page {
  margin: 22vh 22vh 22vh 22vh;
  flex-direction: row;
}
#image img {
  height: 42vh;
  width: 42vh;
  overflow: hidden;
  object-fit: cover;
}
#info img {
  height: 12vh;
}

button {
  background: linear-gradient(#5472cc, #538eae);
  font-weight: 500;
  color: #d4e3f0;
  border-radius: 2px;
  box-shadow: 2px 2px 0 #8e9dcc;
  border: none;
  margin-top: 22px;
  height: 35px;
  width: 15vh;
  cursor: pointer;
}
button a {
  text-decoration: none;
  color: #d4e3f0;
}
button a:hover {
  color: #294598;
}
button:hover {
  color: #294598;
  border-radius: 5px;
}
</style>

