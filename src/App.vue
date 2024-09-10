<script setup lang="ts">
import NavigationMenu from './components/NavigationMenu.vue'
import MainInfoPanel from './components/MainInfoPanel.vue'
import WarninPanel from './components/WarninPanel.vue'
import WeatherBack from './components/WeatherBack.vue'
import DaysForecast from './components/DaysForecast.vue'
import TempForecast from './components/TempForecast.vue'
</script>

<template>
  <WeatherBack />
  <header>
    <NavigationMenu />
  </header>
  <main>
    <MainInfoPanel />
    <WarninPanel />
    <DaysForecast />
    <TempForecast />
  </main>
</template>

<style scoped>
.text-color {
  color: var(--color-font-white);
}

main {
  height: 90vh;
  margin-left: 5vw;
  margin-right: 5vw;
  width: 90%;
  color: var(--color-font-white);
}

header {
  height: 8vh;
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
</style>
