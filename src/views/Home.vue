<template>
  <div class="home">
    <div class="section">
      <h2>Shooter</h2>
      <div class="grid">
        <Games :games="shooters" />
      </div>
    </div>
    <div class="section">
      <h2>MMORPG</h2>
      <div class="grid">
        <Games :games="mmorpgs" />
      </div>
    </div>
    <div class="section">
      <h2>Social</h2>
      <div class="grid">
        <Games :games="socials" />
      </div>
    </div>
    <div class="section">
      <h2>Card Games</h2>
      <div class="grid">
        <Games :games="cards" />
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
      cards: []
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
    const tempShooters = await this.fetchByCategory('shooter')
    const tempMmorpgs = await this.fetchByCategory('mmorpg')
    const tempSocials = await this.fetchByCategory('social')
    const tempCards = await this.fetchByCategory('card')
    this.shooters = tempShooters.slice(0, 8)
    this.mmorpgs = tempMmorpgs.slice(0, 8)
    this.socials = tempSocials.slice(0, 8)
    this.cards = tempCards.slice(0, 8)
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
