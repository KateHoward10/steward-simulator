<template>
  <div class="seat">
    <div v-if="occupied" class="hair" :style="{ backgroundColor: hairColour }"></div>
  </div>
</template>

<script>
export default {
  name: 'Seat',
  props: { occupied: Boolean, hairColour: String }
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
  .hair {
    position: absolute;
    width: 16px;
    height: 8px;
    border-top-left-radius: 8px;
    border-top-right-radius: 8px;
    margin: -8px 4px 0;
  }
</style>
