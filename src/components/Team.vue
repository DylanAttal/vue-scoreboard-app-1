<template>
  <div>
    <h1>{{ teamName }}</h1>
    <p>Update Team Name</p>
    <p>{{ score }}</p>
    <button @click="addPoint(index)">Add Point</button>
    <button @click="subtractPoint(index)">Subtract Point</button>
  </div>
</template>

<script>
export default {
  name: "Team",
  props: {
    teamName: String,
    score: Number,
    addPoint: Function,
    subtractPoint: Function,
    index: Number
  }
};
</script>

<style scoped>
</style>