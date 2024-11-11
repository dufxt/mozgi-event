<script setup lang="ts">
import LanguageSelector from '@/components/LanguageSelector.vue';
import MainLogo from '@/components/MainLogo.vue';
import MobileMenu from '@/components/MobileMenu.vue';
</script>

<template>
  <header class="header">
    <LanguageSelector />
    <MainLogo />
    <MobileMenu />
  </header>
</template>

<style lang="scss" scoped>
.header {
  position: relative;
  display: flex;
  align-items: var(--main-header-align-items);
  justify-content: space-between;
  z-index: 5;
}
</style>
