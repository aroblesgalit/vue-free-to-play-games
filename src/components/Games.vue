<template>
  <div v-for="game in games" :key="game.id" class="box">
    <Game :game="game" />
  </div>
</template>

<script>
import Game from './Game'

export default {
  name: 'Games',
  props: {
    games: Array
  },
  components: {
    Game
  }
}
</script>

<style scoped>
.box {
  width: 100%;
  max-width: 240px;
  border-radius: 10px;
  overflow: hidden;
  background-color: #202a35;
}
</style>
