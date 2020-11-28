<template>
  <div class="seat">
    <div v-if="occupied" class="head" :style="{ backgroundColor: hairColours[Math.random() * hairColours.length | 0] }"></div>
  </div>
</template>

<script>
export default {
  name: 'Seat',
  props: { occupied: Boolean },
  data() {
    return {
      hairColours: ["#222", "#800000", "#cc6600", "#993300", "#ff6600", "#ffcc00", "#999", "#663300"]
    }
  }
}
</script>

<style scoped>
  .seat {
    width: 24px;
    height: 24px;
    background-color: #cc3300;
    color: #ffffcc;
    font-size: 12px;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
    position: relative;
  }
  .head {
    position: absolute;
    width: 16px;
    height: 8px;
    border-top-left-radius: 8px;
    border-top-right-radius: 8px;
    background-color: #000;
    margin: -8px 4px 0;
  }
</style>
