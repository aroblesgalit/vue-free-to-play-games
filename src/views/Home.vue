<template>
  <div class="home">
    <h2>Featured</h2>
    <div class="grid">
      <div class="box">
        <div class="images">
          <img
            src="https://www.freetogame.com/g/1/dauntless-1.jpg"
            alt="screenshot"
          />
          <!-- <img
            src="https://www.freetogame.com/g/1/dauntless-2.jpg"
            alt="screenshot"
          />
          <img
            src="https://www.freetogame.com/g/1/dauntless-3.jpg"
            alt="screenshot"
          />
          <img
            src="https://www.freetogame.com/g/1/dauntless-4.jpg"
            alt="screenshot"
          /> -->
        </div>
        <div class="body">
          <h3>Dauntless</h3>
          <p>
            A free-to-play, co-op action RPG with gameplay similar to Monster
            Hunter.
          </p>
          <div class="details">
            <span>MMORPG</span>
            <span>Windows</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from 'axios'

export default {
  name: 'Home',
  components: {},
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
}

.box {
  width: 100%;
  max-width: 240px;
  border-radius: 10px;
  overflow: hidden;
  background-color: #202a35;
}

.images img {
  max-width: 100%;
}

.box .body {
  padding: 10px 16px 16px;
  text-align: left;
}

.body h3 {
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 10px;
}

.body p {
  font-size: 13px;
  line-height: 1.3em;
  margin-bottom: 10px;
  opacity: 0.8;
}

.body .details {
  display: flex;
  justify-content: space-between;
  font-size: 10px;
  color: #181f25;
  font-weight: bold;
}

.details span {
  background-color: #5b646e;
  padding: 4px 6px;
  border-radius: 4px;
}
</style>
