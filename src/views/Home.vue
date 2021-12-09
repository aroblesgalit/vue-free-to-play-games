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

export default {
  name: 'Home',
  components: {}
}
</script>

<style scoped>
.home {
  padding: 40px 100px;
}

h2 {
  text-align: left;
}
</style>
