<template>
  <div id="nav">
    <div>
      <img alt="Vue logo" src="./assets/logo.png" />
    </div>
    <div>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
  </div>
  <router-view />
</template>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #949eaa;
  background-color: #2c3e50;
}

#nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px 100px;
  background-color: #202a35;
}

#nav img {
  max-width: 30px;
}

#nav a {
  font-weight: bold;
  color: #949eaa;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
