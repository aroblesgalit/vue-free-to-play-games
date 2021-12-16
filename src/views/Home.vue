<template>
  <div class="home">
    <h2>Featured</h2>
    <div class="grid">
      <Games :games="games" />
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
      games: []
    }
  },
  methods: {
    async fetchGames () {
      const res = await axios.get('http://localhost:8080/api/games')
      const data = res.data
      return data
    }
  },
  async created () {
    this.games = await this.fetchGames()
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
