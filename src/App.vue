<script setup lang="ts">
import NavigationMenu from './components/NavigationMenu.vue'
import MainInfoPanel from './components/MainInfoPanel.vue'
import WarningPanel from './components/WarningPanel.vue'
import WeatherBack from './components/WeatherBack.vue'
import DaysForecast from './components/DaysForecast.vue'
import TempForecast from './components/TempForecast.vue'
import UVPanel from "./components/UVPanel.vue";
import HumidityPanel from "./components/HumidityPanel.vue";
import {verify} from "node:crypto";
import {onMounted, onUnmounted, ref} from "vue";

const opacity = ref(1);

const handleScroll = () => {
  const scrollY = window.scrollY; // Текущая позиция скролла
  const fadeStart = 100; // Начало прозрачности
  const fadeEnd = 200;  // Полностью прозрачный
  if (scrollY <= fadeStart) {
    opacity.value = 1; // Полностью видимый
  } else if (scrollY >= fadeEnd) {
    opacity.value = 0; // Полностью прозрачный
  } else {
    opacity.value = 1 - (scrollY - fadeStart) / (fadeEnd - fadeStart);
  }
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});

</script>

<template>
  <WeatherBack />
  <header>
    <NavigationMenu :style="{ opacity: opacity }"/>
  </header>
  <main>
    <div class="container">
      <MainInfoPanel  />
      <WarningPanel />
      <DaysForecast />
      <div class="panel_grid">
        <UVPanel/>
        <HumidityPanel/>
      </div>

      <TempForecast />
    </div>

  </main>
</template>

<style scoped>

.text-color {
  color: var(--color-font-white);
}

main {
  overflow: auto;
  height: 200vh;
  width: 100%;
  color: var(--color-font-white);
}

.container{
  margin-left: 5vw;
  margin-right: 5vw;
  width: 90%;
  height: 100%;
}


header {
  right: 0;
  position: fixed;
  height: 5vh;
  width: 100%;
  line-height: 1.5;
  display: flex;
  align-items: center;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    min-width: 100vw;
    display: flex;
    place-items: center;
    height: 8vh;
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
.panel_grid{
  display: flex;
  align-content: space-between;
  justify-content: space-between;
}
</style>
