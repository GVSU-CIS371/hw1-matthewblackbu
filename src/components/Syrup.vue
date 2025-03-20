<template>
  <div class="syrup" 
  :style="{ backgroundColor: currentSyrup.color,
    height: currentSyrup.name == 'No Syrup' ? '0%' : '20%' 
  }"></div>
</template>

<script setup lang="ts">
  import { currentSyrup } from '../stores/beverage';
</script>



<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  background-color: #c6c6c6;
  position: relative;
  width: 100%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
.nosyrup{
  height: 00%;
}
</style>
