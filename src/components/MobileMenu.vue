<template>
  <div class="mobile-menu">
    <div />
    <div />
  </div>
</template>

<style lang="scss" scoped>
.mobile-menu {
  visibility: var(--mobile-menu-visibility);
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  width: var(--lenguage-selector-size);

  div {
    width: 22px;
    height: 1px;
    background-color: #000;

    &:not(:last-child) {
      margin-bottom: 8px;
    }
  }
}
</style>
