<template>
  <div id="app">
    <div id="nav"></div>
    <router-view />
  </div>
</template>

<style>
* {
  padding: 0;
  margin: 0;
  list-style: none;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  max-width: 650px;
  margin: 0 auto;
  min-height: 100%;
  overflow: hidden;
  box-shadow: rgba(0, 0, 0, 0.5) 0px 1px 10px;
  background: #ededed;
}
/* 
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
} */
</style>
