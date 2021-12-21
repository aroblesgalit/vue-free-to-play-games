<template>
  <div class="home">
    <div class="section">
      <h2>Shooter</h2>
      <div class="grid">
        <Games :games="shooters.slice(0, 8)" />
      </div>
    </div>
    <div class="section">
      <h2>MMORPG</h2>
      <div class="grid">
        <Games :games="mmorpgs.slice(0, 8)" />
      </div>
    </div>
    <div class="section">
      <h2>Social</h2>
      <div class="grid">
        <Games :games="socials.slice(0, 8)" />
      </div>
    </div>
    <div class="section">
      <h2>Card Game</h2>
      <div class="grid">
        <Games :games="cards.slice(0, 8)" />
      </div>
    </div>
    <div class="section">
      <h2>MOBA</h2>
      <div class="grid">
        <Games :games="mobas.slice(0, 8)" />
      </div>
    </div>
    <div class="section">
      <h2>Fighting</h2>
      <div class="grid">
        <Games :games="fightings.slice(0, 8)" />
      </div>
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
      shooters: [],
      mmorpgs: [],
      socials: [],
      cards: [],
      mobas: [],
      fightings: []
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
    // this.allGames = await this.fetchAllGames()
    this.shooters = await this.fetchByCategory('shooter')
    this.mmorpgs = await this.fetchByCategory('mmorpg')
    this.socials = await this.fetchByCategory('social')
    this.cards = await this.fetchByCategory('card')
    this.mobas = await this.fetchByCategory('moba')
    this.fightings = await this.fetchByCategory('fighting')
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
