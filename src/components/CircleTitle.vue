<script setup lang="ts">
import IconShowreel from '@/assets/icons/showreel.svg';
</script>

<template>
  <div class="circle-title">
    <IconShowreel class="icon" />
  </div>
</template>

<style lang="scss" scoped>
.circle-title {
  position: absolute;
  right: var(--circle-title-right);
  bottom: var(--circle-title-bottom);
  width: var(--circle-title-size);
  height: var(--circle-title-size);

  @media (hover: hover) {
    &:hover {
      .icon {
        animation-play-state: running;
        transform: rotate(0.04turn);
      }
    }
  }

  .icon {
    width: 100%;
    height: 100%;
    animation: rotate 4s linear infinite paused;
    transition: transform 0.4s ease-out;
  }
}

@keyframes rotate {
  to {
    rotate: -1turn;
  }
}
</style>
