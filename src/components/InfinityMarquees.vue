<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted, type CSSProperties } from 'vue';
import InfiniteMarquee from '@/components/InfiniteMarquee.vue';

const marqueesWidth = ref<number>(0);
const marqueesRotation = ref<number>(0);

const marqueesStyle = computed<CSSProperties>(() => ({
  width: `${marqueesWidth.value}px`,
  transform: `translate(-50%, -50%) rotate(${marqueesRotation.value}deg)`,
}));

function calculateWidth(): void {
  marqueesWidth.value = Math.sqrt(window.innerWidth ** 2 + window.innerHeight ** 2) + 100;
}

function calculateRotation(): void {
  const angleRadians = Math.atan2(-window.innerHeight, window.innerWidth);

  marqueesRotation.value = angleRadians * (180 / Math.PI);
}

function resize(): void {
  calculateWidth();
  calculateRotation();
}

onMounted(() => {
  resize();
  window.addEventListener('resize', resize);
});

onUnmounted(() => {
  window.removeEventListener('resize', resize);
});
</script>

<template>
  <div class="marquees" :style="marqueesStyle">
    <InfiniteMarquee :reverse="true" />
    <InfiniteMarquee />
  </div>
</template>

<style lang="scss" scoped>
.marquees {
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  transform-origin: center;
  z-index: 1;
}
</style>
