<template>
  <div class="images">
    <img :src="game.thumbnail" alt="screenshot" />
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
    <h3>{{ game.title }}</h3>
    <p>{{ game.short_description }}</p>
    <div class="details">
      <span>{{ game.genre }}</span>
      <span>{{ game.platform }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Game',
  props: {
    game: Object
  }
}
</script>

<style scoped>
.images img {
  max-width: 100%;
}

.body {
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