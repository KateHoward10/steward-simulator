<template>
  <div class="seat">
    <div v-if="occupied" class="head"></div>
  </div>
</template>

<script>
export default {
  name: 'Seat',
  props: { occupied: Boolean }
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
