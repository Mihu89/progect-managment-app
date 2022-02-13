<template>
  <v-app>
    <v-main class="ma-4">
      <Navbar/>
    <!-- <div id="nav">
      <router-link to="/">Dasboard</router-link> |
      <router-link to="/projects">Projects</router-link>
      <router-link to="/team">Team</router-link>
    </div> -->
      <router-view/>
    </v-main>
  </v-app>
</template>
<script>
import Navbar from '@/components/Navbar'
export default {
  name: 'App',
  components: {
    Navbar
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
