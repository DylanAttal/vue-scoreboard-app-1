<template>
  <div>
    <h1>Congratulations!</h1>
    <p>The Team won the sports game!</p>
    <b-button>Reset Game</b-button>
  </div>
</template>

<script>
export default {
  name: 'Winner'
}
</script>

<style scoped>
div {
  background-color: #eee;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 10;
  height: 350px;
  width: 550px;
  border: 1px solid grey;
  border-radius: 4px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
