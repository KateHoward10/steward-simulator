<template>
  <div class="seat">
    {{ seat }}
  </div>
</template>

<script>
export default {
  name: 'Seat',
  props: { seat: String }
}
</script>

<style scoped>
  .seat {
    width: 30px;
    height: 30px;
    background-color: #cc3300;
    color: #ffffcc;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
  }
</style>
