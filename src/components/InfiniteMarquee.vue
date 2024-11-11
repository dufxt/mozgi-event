<script setup lang="ts">
import { Vue3Marquee } from 'vue3-marquee';

defineProps<{
  reverse?: boolean;
}>();
</script>

<template>
  <div :class="{ reverse }" class="marquee">
    <Vue3Marquee :clone="true">
      <h2 class="marquee-text">Full-cycle event agency</h2>
    </Vue3Marquee>
  </div>
</template>

<style lang="scss" scoped>
.marquee {
  &.reverse {
    margin-bottom: var(--marquee-margin);
    transform: scaleX(-1) scaleY(-1);
  }

  .marquee-text {
    font-size: var(--marquee-font-size);
    line-height: 110%;
    font-style: italic;
    text-transform: uppercase;
    -webkit-text-stroke: 1px var(--text-color);
    color: transparent;
    overflow-y: hidden;
    opacity: 0.1;
  }
}
</style>
