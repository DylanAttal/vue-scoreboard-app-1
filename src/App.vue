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
    <div class="new-team-wrapper">
      <div class="new-team-container">
        <h2>Add New Team</h2>
        <b-form-input v-model="newTeam" />
        <b-button variant="info" @click="createNewTeam"
          >Create New Team</b-button
        >
      </div>
    </div>
    <Winner />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Team from './components/Team.vue'
import Winner from './components/Winner.vue'

export default {
  name: 'app',
  components: {
    Header,
    Team,
    Winner
  },
  data() {
    return {
      teams: [
        {
          teamName: 'Gators',
          score: 0
        },
        {
          teamName: 'Seminoles',
          score: 0
        }
      ],
      newTeam: ''
    }
  },
  methods: {
    addPoint(index) {
      this.teams[index].score++
    },
    subtractPoint(index) {
      this.teams[index].score--
    },
    createNewTeam() {
      this.teams.push({ teamName: this.newTeam, score: 0 })
      this.newTeam = ''
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  margin: 0;
}

.teams-container {
  margin-top: 3rem;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}

.new-team-wrapper {
  margin-top: 3rem;
  display: flex;
  flex-direction: row;
  justify-content: center;
}

.new-team-container {
  width: 30%;
}
</style>
