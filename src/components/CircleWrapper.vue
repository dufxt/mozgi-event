<script setup lang="ts">
import CircleTitle from '@/components/CircleTitle.vue';
</script>

<template>
  <div class="circle-wrapper">
    <div class="circle" />
    <CircleTitle />
  </div>
</template>

<style lang="scss" scoped>
.circle-wrapper {
  position: fixed;
  left: 50%;
  top: 50%;
  width: var(--circle-size);
  height: var(--circle-size);
  transform: translate(-50%, -50%);
  z-index: 2;

  .circle {
    width: 100%;
    height: 100%;
    background-color: var(--circle-color);
    border-radius: 50%;
    filter: blur(var(--circle-blur));
  }
}
</style>
