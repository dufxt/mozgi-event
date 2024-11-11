<script setup lang="ts">
defineProps<{
  title: string;
  path: string;
}>();
</script>

<template>
  <RouterLink :to="path" class="menu-link">
    {{ title }}
  </RouterLink>
</template>

<style lang="scss" scoped>
.menu-link {
  position: relative;
  font-weight: 600;
  font-size: var(--menu-link-font-size);
  line-height: 140%;
  text-transform: lowercase;
  text-decoration: none;
  color: var(--text-color);
  transition: color 0.3s ease-out;
  z-index: 5;

  @media (hover: hover) {
    &:hover {
      color: var(--menu-link-hover-color);

      &::after {
        width: 100%;
      }
    }
  }

  &::after {
    content: '';
    position: absolute;
    left: 0;
    bottom: -4px;
    width: 0;
    height: 2px;
    background-color: var(--menu-link-hover-color);
    transition: width 0.3s ease;
  }
}
</style>
