<template >
  <div id="app">
    <router-link to="/">Home</router-link>|
    <router-link to="/catalog">Catalog</router-link>
    <router-view />
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=MuseoModerno&display=swap");
#app {
  font-family: "MuseoModerno", cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #a52a2a;
  /* background-color: #FFE4C4; */
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
/* .grid-container {
  background-color: #FFE4C4;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr;
  gap: 1px 1px;
  grid-template-areas: 
  "nav nav nav" 
  "main main main" 
  "footer footer footer";
}
.nav{
  grid-area: nav;
}
.main{
  grid-area: main;
}
.footer{
  grid-area: footer;
} */
</style>
