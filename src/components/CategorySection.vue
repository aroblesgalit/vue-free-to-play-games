<template>
  <div class="section">
    <h2>{{ category }}</h2>
    <div class="grid">
      <Games
        :games="games.filter(game => game.genre == `${category}`).slice(0, 8)"
      />
    </div>
  </div>
</template>

<script>
import Games from './Games.vue'

export default {
  name: 'CategorySection',
  props: {
    category: String,
    games: Array
  },
  components: {
    Games
  }
}
</script>

<style scoped>
.section {
  margin-bottom: 60px;
}

h2 {
  text-align: left;
  margin-bottom: 30px;
}

.grid {
  display: flex;
  flex-wrap: nowrap;
  gap: 20px;
  overflow-x: scroll;
}
</style>
