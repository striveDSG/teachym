<template>
  <div id="app">
    <div id="nav">
      <router-link to="/" tag="a">Home</router-link> |
      <router-link :to="rout" replace>About</router-link>
      <button @click="handlerClick">about</button>
    </div>
    <router-view />
  </div>
</template>

<script>
export default {
  data() {
    return {
      rout: "/about",
    };
  },
  methods: {
    handlerClick() {
      // this.$router.push("/about");
      let id = 2,
        name = "yt";
      this.$router.push({
        path: "/about",
        query: {
          id,
          name,
        },
      });
    },
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
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
</style>
