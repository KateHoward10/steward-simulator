<template>
  <div class="punter">
    <div class="head" :style="{ backgroundColor: punter.hair || 'tranparent' }"></div>
    <div class="body" :style="{ backgroundColor: punter.body || 'tranparent' }"></div>
  </div>
</template>

<script>
export default {
  name: 'Punter',
  props: { punter: Object }
}
</script>

<style scoped>
  .punter {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .head {
    width: 16px;
    height: 8px;
    border-top-left-radius: 8px;
    border-top-right-radius: 8px;
  }
  .body {
    width: 16px;
    height: 10px;
  }
</style>
