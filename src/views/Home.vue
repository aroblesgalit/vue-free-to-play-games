<template>
  <div class="home">
    <CategorySection category="Shooter" :games="allGames" />
    <!-- <div class="section">
      <h2>Shooter</h2>
      <div class="grid">
        <Games
          :games="allGames.filter(game => game.genre == 'Shooter').slice(0, 8)"
        />
      </div>
    </div>
    <div class="section">
      <h2>MMORPG</h2>
      <div class="grid">
        <Games
          :games="allGames.filter(game => game.genre == 'MMORPG').slice(0, 8)"
        />
      </div>
    </div>
    <div class="section">
      <h2>Social</h2>
      <div class="grid">
        <Games
          :games="allGames.filter(game => game.genre == 'Social').slice(0, 8)"
        />
      </div>
    </div>
    <div class="section">
      <h2>Card Game</h2>
      <div class="grid">
        <Games
          :games="
            allGames.filter(game => game.genre == 'Card Game').slice(0, 8)
          "
        />
      </div>
    </div>
    <div class="section">
      <h2>MOBA</h2>
      <div class="grid">
        <Games
          :games="allGames.filter(game => game.genre == 'MOBA').slice(0, 8)"
        />
      </div>
    </div>
    <div class="section">
      <h2>Fighting</h2>
      <div class="grid">
        <Games
          :games="allGames.filter(game => game.genre == 'Fighting').slice(0, 8)"
        />
      </div>
    </div> -->
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'
import Games from '../components/Games'
import CategorySection from '../components/CategorySection.vue'

export default {
  name: 'Home',
  components: {
    Games,
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

.section {
  margin-bottom: 60px;
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
