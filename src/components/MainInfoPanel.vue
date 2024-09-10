<script setup lang="ts">
import IconArrow from './icons/IconArrow.vue'
import IconSheet from './icons/IconSheet.vue'
</script>
<template>
  <div class="main_info_panel">
    <h2 class="siti_text">Siti</h2>
    <div class="location_block">
      <h2 class="location_text">Location Service</h2>
      <IconArrow />
    </div>
    <h1 class="temp_text">60°</h1>
    <div class="cloudy_min_max_temp">
      <h3>Cloudy</h3>
      <h3>50°/60°</h3>
    </div>
    <div class="aqi_panel">
      <IconSheet />
      <h2>AQI</h2>
      <h2>25</h2>
    </div>
  </div>
</template>
<style scoped>
.main_info_panel {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 24vh;
}

.siti_text {
  font-size: 3vh;
}

.location_block {
  grid-gap: 2vw;
  display: flex;
  align-items: center;
}

.location_text {
  font-size: 1.5vh;
}

.temp_text {
  margin-top: -2vh;
  margin-bottom: -1vh;
  font-size: 15vh;
  font-weight: 300;
  padding-left: 2vw;
}

.cloudy_min_max_temp {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 2.2vh;
  line-height: 4vh;
}

.aqi_panel {
  margin-top: 1vh;
  display: flex;
  align-items: center;
  grid-gap: 2vw;
  background: var(--color-back-aqi);
  padding-left: 15px;
  padding-right: 15px;
  border-radius: 20px;
  font-weight: 100;
  font-size: 1.5vh;
}

.aqi_panel svg {
  height: 3vh;
}
</style>
