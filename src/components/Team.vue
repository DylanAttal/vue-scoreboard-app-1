<template>
  <div>
    <h1>{{ teamName }}</h1>
    <p>Update Team Name</p>
    <b-form-input
      v-model="newTeamName"
      @keyup="updateTeamName(newTeamName, index)"
    />
    <p class="score">{{ score }}</p>
    <b-button variant="success" @click="addPoint(index)">Add Point</b-button>
    <b-button variant="danger" @click="subtractPoint(index)"
      >Subtract Point</b-button
    >
  </div>
</template>

<script>
export default {
  name: 'Team',
  props: {
    teamName: String,
    score: Number,
    addPoint: Function,
    subtractPoint: Function,
    updateTeamName: Function,
    index: Number
  },
  data() {
    return {
      newTeamName: this.teamName
    }
  }
}
</script>

<style scoped>
.score {
  margin-top: 1rem;
  font-size: 1.5rem;
}
</style>
