<template>
  <div class="section">
    <div>
      <h2>{{ category }}</h2>
      <router-link :to="'/category/' + category.toLowerCase()"
        >See all</router-link
      >
    </div>
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
