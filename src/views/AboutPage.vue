<script setup lang="ts">
import MenuLink from '@/components/MenuLink.vue';
</script>

<template>
  <main class="about">
    <MenuLink title="Back" path="/" />
  </main>
</template>

<style lang="scss" scoped>
.about {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  background-color: var(--bg-color);
}
</style>
