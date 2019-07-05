<template>
  <div id="app">
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <h1
        to='/'
        tag='span'
        style='cursor: pointer'>
        Album
        </h1>
      </v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>

    <Home/>
     
  </div>
</template>

<script>
import Home from "./components/Home";

export default {
  name: "App",
  components: {
    Home
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>