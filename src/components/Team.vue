<template>
  <div>
    <h1>{{ teamName }}</h1>
    <p>Update Team Name</p>
    <p>{{ score }}</p>
    <button>Add Point</button>
    <button>Subtract Point</button>
  </div>
</template>

<script>
export default {
  name: "Team",
  props: {
    teamName: String,
    score: Number
  }
};
</script>

<style scoped>
</style>