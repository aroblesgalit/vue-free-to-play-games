<template>
  <div id="category">
    <h1>{{ name.toUpperCase() }}</h1>
  </div>
</template>

<script>
export default {
  name: 'Category',
  data () {
    return {
      name: ''
    }
  },
  created () {
    console.log(this.$route)
    this.name = this.$route.params.name
  }
}
</script>

<style scoped>
#category {
  padding: 40px 100px;
}
</style>
