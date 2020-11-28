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
    width: 24px;
    height: 24px;
    background-color: #cc3300;
    color: #ffffcc;
    font-size: 12px;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
  }
</style>
