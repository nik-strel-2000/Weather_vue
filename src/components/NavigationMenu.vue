<script setup lang="ts">
import IconPlus from './icons/IconPlus.vue'
import IconMenu from './icons/IconMenu.vue'
</script>

<template>
  <div class="main-menu">
    <div class="left-item">{{}}</div>
    <div class="right-item">
      <IconPlus class="icon-size-plus" />
      <IconMenu class="icon-size-menu" />
    </div>
  </div>
</template>

<style scoped>
.main-menu {
  color: var(--color-font-white);
  top: 0;
  width: 100%;
  height: 2vh;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 30px;
  padding-right: 30px;
  padding-left: 30px;
}

.left-item {
  font-size: 3vh;
}

.right-item {
  display: flex;
  align-items: center;
  grid-gap: 30px;
}

.le .icon-size-plus {
  height: 3vh;
}

.icon-size-menu {
  height: 4vh;
}
</style>
