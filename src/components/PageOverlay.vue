<script setup lang="ts">
import { PageOverlayAnimatons, type TPageOverlayAnimation } from '@/consts';

const props = defineProps<{
  animation: TPageOverlayAnimation;
}>();

const emit = defineEmits<{
  (event: 'clearAnimation'): void;
}>();

function animationEnd(): void {
  if (props.animation === PageOverlayAnimatons.END) {
    emit('clearAnimation');
  }
}
</script>

<template>
  <div :class="animation" class="overlay-wrapper">
    <div class="overlay" @animationend="animationEnd" />
  </div>
</template>

<style lang="scss" scoped>
.overlay-wrapper {
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  z-index: 6;
  visibility: hidden;

  &.start,
  &.end {
    visibility: visible;
  }

  &.start {
    .overlay {
      animation: overlay-start ease-in-out 1s forwards;
    }
  }

  &.end {
    .overlay {
      animation: overlay-end ease-in-out 0.6s forwards;
    }
  }

  .overlay {
    position: absolute;
    left: 0;
    top: 0;
    width: 0;
    height: 100%;
    background-color: var(--page-overlay-bg-color);
  }
}

@keyframes overlay-start {
  20% {
    width: 0;
  }
  40% {
    width: 0;
  }
  100% {
    width: 100%;
  }
}

@keyframes overlay-end {
  0% {
    left: 0;
    width: 100%;
  }
  100% {
    width: 0;
    left: 100%;
  }
}
</style>
