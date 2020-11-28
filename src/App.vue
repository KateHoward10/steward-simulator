<template>
  <Seat v-for="(seat, index) in seats" :key="index" :seat="seat"></Seat>
</template>

<script>
import Seat from './components/Seat.vue'

export default {
  name: 'App',
  data() {
    return {
      seats: Array.from(Array(32).keys()).reverse().map(n => `A${n+1}`)
    }
  },
  components: {
    Seat
  }
}
</script>

<style>
body {
  padding: 0;
  background-color: #ffffcc;
  display: flex;
  justify-content: center;
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  display: grid;
  margin: 40px 0;
  grid-template-columns: repeat(32, 30px);
  grid-template-rows: repeat(8, 30px);
  grid-gap: 5px;
}
</style>
