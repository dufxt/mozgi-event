<script setup lang="ts">
const languages = ['ru', 'ua'];
</script>

<template>
  <div class="selector-wrapper">
    <div class="selector">
      <img src="@/assets/icons/tongue.png" alt="tongue" />
    </div>

    <ul class="options">
      <li class="option" v-for="(lang, i) in languages" :key="i" :style="{ '--order': i + 1 }">
        {{ lang }}
      </li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
.selector-wrapper {
  position: relative;
  display: flex;
  align-items: center;
  width: var(--lenguage-selector-size);
  padding-top: var(--lenguage-selector-margin-top);

  --order: 1;

  &:hover {
    .options {
      pointer-events: auto;

      .option {
        opacity: 1;
        transform: translateX(0);
      }
    }
  }

  .selector {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-shrink: 0;
    width: var(--lenguage-selector-size);
    height: var(--lenguage-selector-size);
    border: 1px solid rgba(255, 255, 255, 0.12);
    border-radius: 50%;
    cursor: pointer;

    img {
      width: 15px;
    }
  }

  .options {
    position: absolute;
    top: 50%;
    left: 100%;
    display: flex;
    align-items: center;
    height: 100%;
    transform: translateY(calc(-50% + var(--lenguage-selector-margin-top) / 2));
    pointer-events: none;

    .option {
      margin-left: 10px;
      font-size: var(--lenguage-selector-option-font-size);
      line-height: 100%;
      text-transform: uppercase;
      cursor: pointer;
      opacity: 0;
      transform: translateX(-20px);
      transition: all 0.3s ease;
      transition-delay: calc(var(--order) * 0.2s);
    }
  }
}
</style>
