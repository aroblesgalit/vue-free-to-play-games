<template>
  <div class="home">
    <CategorySection category="Shooter" :games="allGames" />
    <CategorySection category="MMORPG" :games="allGames" />
    <CategorySection category="Social" :games="allGames" />
    <CategorySection category="Card Game" :games="allGames" />
    <CategorySection category="MOBA" :games="allGames" />
    <CategorySection category="Fighting" :games="allGames" />
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'
import CategorySection from '../components/CategorySection.vue'

export default {
  name: 'Home',
  components: {
    CategorySection
  },
  data () {
    return {
      allGames: []
    }
  },
  methods: {
    async fetchAllGames () {
      const res = await axios.get('http://localhost:8080/api/games')
      const data = res.data
      return data
    },
    async fetchByCategory (category) {
      const res = await axios.get(
        `http://localhost:8080/api/games?category=${category}`
      )
      const data = res.data
      return data
    }
  },
  async created () {
    this.allGames = await this.fetchAllGames()
  }
}
</script>

<style scoped>
.home {
  padding: 40px 100px;
}
</style>
