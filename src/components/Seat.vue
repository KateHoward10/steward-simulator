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
    width: 28px;
    height: 28px;
    background-color: #cc3300;
    color: #ffffcc;
    font-size: 14px;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
  }
</style>
