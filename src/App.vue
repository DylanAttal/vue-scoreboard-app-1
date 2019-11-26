<template>
  <div id="app">
    <Header />
    <div class="teams-container">
      <Team />
      <Team />
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Team from "./components/Team.vue";

export default {
  name: "app",
  components: {
    Header,
    Team
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
}

body {
  margin: 0;
}

.teams-container {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
</style>
