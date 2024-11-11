<script setup lang="ts">
import IconLogo from '@/assets/icons/logo.svg';
</script>

<template>
  <div class="logo">
    <IconLogo class="icon" />
  </div>
</template>

<style lang="scss" scoped>
.logo {
  .icon {
    width: var(--main-logo-width);

    &:deep(.fill) {
      animation: fill-logo 3s forwards;
    }
  }
}

@keyframes fill-logo {
  0% {
    clip-path: inset(100% 0 0 0);
  }
  100% {
    clip-path: inset(0 0 0 0);
  }
}
</style>
