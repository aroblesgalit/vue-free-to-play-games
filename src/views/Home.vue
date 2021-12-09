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
  padding: 10px;
  text-align: left;
}

.body h3 {
  font-size: 16px;
  font-weight: bold;
  margin-bottom: 10px;
}

.body p {
  font-size: 14px;
  margin-bottom: 10px;
}

.body .details {
  display: flex;
  justify-content: space-between;
  font-size: 12px;
}
</style>
