<script setup lang="ts">
import MenuLink from '@/components/MenuLink.vue';
import { MenuLinkPositions } from '@/consts';

type TLink = {
  title: string;
  path: string;
  position: MenuLinkPositions;
};

const links: TLink[] = [
  {
    title: 'Where?',
    path: '/about',
    position: MenuLinkPositions.LEFT,
  },
  {
    title: 'What?',
    path: '/about',
    position: MenuLinkPositions.RIGHT,
  },
  {
    title: 'Who?',
    path: '/about',
    position: MenuLinkPositions.BOTTOM,
  },
];
</script>

<template>
  <nav class="menu">
    <ul>
      <li v-for="link in links" :key="link.position" :class="link.position">
        <MenuLink :title="link.title" :path="link.path" />
      </li>
    </ul>
  </nav>
</template>

<style lang="scss" scoped>
.menu {
  display: var(--main-menu-display);

  li {
    position: fixed;
    line-height: var(--menu-link-font-size);
    z-index: 5;

    &.left {
      left: var(--menu-vertical-link-margin);
      top: 50%;
      transform-origin: 0 0;
      transform: rotate(-90deg) translateX(-50%);
    }

    &.right {
      right: var(--menu-vertical-link-margin);
      top: 50%;
      transform-origin: top right;
      transform: rotate(90deg) translateX(50%);
    }

    &.bottom {
      left: 50%;
      bottom: var(--menu-gorizontal-link-margin);
      transform: translateX(-50%);
    }
  }
}
</style>
