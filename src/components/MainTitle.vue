<script setup lang="ts">
import { computed, onMounted, onUnmounted, ref } from 'vue';

type TTitleCoordinates = {
  x: number;
  y: number;
};

const movementFactor = 60;

const titleCoordinates = ref<TTitleCoordinates | null>(null);

const titleTransform = computed<string>(() => {
  if (!titleCoordinates.value) return 'translate(-50%, -50%)';

  return `translate(-50%, -50%) translate(${titleCoordinates.value.x}px, ${titleCoordinates.value.y}px)`;
});

function setCoordinates(e: MouseEvent): void {
  titleCoordinates.value = {
    x: e.pageX / movementFactor,
    y: e.pageY / movementFactor,
  };
}

onMounted(() => {
  window.addEventListener('mousemove', setCoordinates);
});

onUnmounted(() => {
  window.removeEventListener('mousemove', setCoordinates);
});
</script>

<template>
  <h1 class="title" :style="{ transform: titleTransform }">Full-cycle <br />event agency</h1>
</template>

<style lang="scss" scoped>
.title {
  position: fixed;
  left: 50%;
  top: 50%;
  width: var(--main-title-width);
  font-size: var(--main-title-font-size);
  font-weight: 700;
  line-height: 110%;
  text-align: center;
  text-transform: uppercase;
  transform: translate(-50%, -50%);
  z-index: 3;
}
</style>
