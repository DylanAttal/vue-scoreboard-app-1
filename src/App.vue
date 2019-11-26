<template>
  <div id="app">
    <Header />
    <div class="teams-container">
      <Team
        v-for="(team, index) in teams"
        :key="index"
        :teamName="team.teamName"
        :score="team.score"
        :addPoint="addPoint"
        :subtractPoint="subtractPoint"
        :index="index"
      />
    </div>
    <div class="new-team-container">
      <h2>Add New Team</h2>
      <input v-model="newTeam" />
      <button @click="createNewTeam">Create New Team</button>
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
  },
  data() {
    return {
      teams: [
        {
          teamName: "Gators",
          score: 0
        },
        {
          teamName: "Seminoles",
          score: 0
        }
      ],
      newTeam: ""
    };
  },
  methods: {
    addPoint(index) {
      this.teams[index].score++;
    },
    subtractPoint(index) {
      this.teams[index].score--;
    },
    createNewTeam() {
      this.teams.push({ teamName: this.newTeam, score: 0 });
      this.newTeam = "";
    }
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
