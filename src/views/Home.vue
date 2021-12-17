<template>
  <div class="home">
    <h2>Featured</h2>
    <div class="grid">
      <Games :games="allGames" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'
import Games from '../components/Games'

export default {
  name: 'Home',
  components: {
    Games
  },
  data () {
    return {
      allGames: [],
      shooters: []
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
        `https://www.freetogame.com/api/games?category=${category}`
      )
      const data = res.data
      return data
    }
  },
  async created () {
    this.allGames = await this.fetchAllGames()
    this.shooters = await this.fetchByCategory('shooters')
  }
}
</script>

<style scoped>
.home {
  padding: 40px 100px;
}

h2 {
  text-align: left;
  margin-bottom: 30px;
}

.grid {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
</style>
