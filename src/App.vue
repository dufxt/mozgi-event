<script setup lang="ts">
import { ref } from 'vue';
import { RouterView } from 'vue-router';
import PageOverlay from '@/components/PageOverlay.vue';
import { PageOverlayAnimatons, type TPageOverlayAnimation } from '@/consts';

const overlayAnimation = ref<TPageOverlayAnimation>(null);

function setOverlayAnimation(animation: TPageOverlayAnimation): void {
  if (overlayAnimation.value === null && animation === PageOverlayAnimatons.END) return;

  overlayAnimation.value = animation;
}
</script>

<template>
  <div class="app">
    <RouterView v-slot="{ Component }">
      <Transition
        name="overlay"
        mode="out-in"
        @before-leave="setOverlayAnimation(PageOverlayAnimatons.START)"
        @after-enter="setOverlayAnimation(PageOverlayAnimatons.END)"
      >
        <Component :is="Component" />
      </Transition>
    </RouterView>

    <PageOverlay :animation="overlayAnimation" @clear-animation="setOverlayAnimation(null)" />
  </div>
</template>

<style lang="scss" scoped>
.app {
  position: relative;
  width: 100vw;
  height: 100vh;
  padding: var(--main-padding);
  background-color: var(--bg-color);
  font-family: var(--main-font-family), sans-serif;
  color: var(--text-color);

  .overlay-leave-active {
    transition: 1s ease-out;
  }

  .overlay-enter-active {
    transition: 0.3s ease-out;
  }
}
</style>
