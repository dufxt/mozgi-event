<script setup lang="ts">
import MainHeader from '@/components/MainHeader.vue';
import MainMenu from '@/components/MainMenu.vue';
import InfinityMarquees from '@/components/InfinityMarquees.vue';
import CircleWrapper from '@/components/CircleWrapper.vue';
import MainTitle from '@/components/MainTitle.vue';
</script>

<template>
  <div class="home">
    <MainHeader />
    <MainMenu />

    <main>
      <InfinityMarquees />
      <CircleWrapper />
      <MainTitle />
    </main>
  </div>
</template>

<style lang="scss" scoped>
.home {
  width: 100%;
  height: 100%;
}
</style>
