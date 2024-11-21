<script setup lang="ts">
import NavigationMenu from './components/NavigationMenu.vue'
import MainInfoPanel from './components/MainInfoPanel.vue'
import WarningPanel from './components/WarningPanel.vue'
import WeatherBack from './components/WeatherBack.vue'
import DaysForecast from './components/DaysForecast.vue'
import TempForecast from './components/TempForecast.vue'
import UVPanel from "@/components/UVPanel.vue";
import HumidityPanel from "@/components/HumidityPanel.vue";
import {verify} from "node:crypto";
</script>

<template>
  <WeatherBack />
  <header>
    <v-icon icon="mdi-account-circle-outline" start></v-icon>
    <!--Add trigger download for Heading-->
    <NavigationMenu />
  </header>
  <main>
    <MainInfoPanel />
    <WarningPanel />
    <DaysForecast />
    <div class="panel_grid">
      <UVPanel/>
      <HumidityPanel/>
    </div>

    <TempForecast />
  </main>
</template>

<style scoped>
.text-color {
  color: var(--color-font-white);
}

main {
  overflow: auto;
  height: 100vh;
  margin-left: 5vw;
  margin-right: 5vw;
  width: 90%;
  color: var(--color-font-white);
}

::-webkit-scrollbar {
  display: none !important;
  width: none !important;
}
header {
  right: 0;
  position: fixed;
  height: 5vh;
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
