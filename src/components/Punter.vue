<template>
  <div class="punter">
    <div class="head" :style="{ backgroundColor: hairColour }"></div>
    <div class="body" :style="{ backgroundColor: bodyColour }"></div>
  </div>
</template>

<script>
export default {
  name: 'Punter',
  props: { hairColour: String },
  data() {
    return {
      bodyColour: 'hsl(' + (Math.random() * 360) + ', 80%, 40%)'
    }
  }
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
