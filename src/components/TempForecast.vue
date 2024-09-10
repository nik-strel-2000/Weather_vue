<script setup lang="ts">
import IconRainCloud from './icons/weather/IconRainCloud.vue'
import { ref, computed, onMounted } from 'vue'

// Пример данных
const temperatures = [50, 47, 45, 44, 45, 46]
const windSpeeds = [11, 10, 12, 15, 16, 14]
const times = ['Now', '12:00', '13:00', '14:00', '15:00', '16:00']

// Расчет точек для графика
const points = ref(
  temperatures.map((temp, index) => ({
    x: 40 + index * 83, // Расположение по оси x
    y: 0 - (temp - 40) * 2 // Расположение по оси y
  }))
)

// Формируем строку координат для polyline
const linePoints = computed(() => points.value.map((point) => `${point.x},${point.y}`).join(' '))

// Вычисляемое свойство для динамического стиля margin-bottom
const dynamicMarginBottoms = ref<string[]>([])

const updateMarginBottom = (index: number) => {
  dynamicMarginBottoms.value[index] = `${temperatures[index] - 30}px`
}

const computedMarginBottom = (index: number) => {
  return dynamicMarginBottoms.value[index] || '10px'
}

onMounted(() => {
  temperatures.forEach((_, index) => updateMarginBottom(index))
})
</script>
<template>
  <div class="panel_info_forecast">
    <div class="panel_info_forecast_header">
      <div class="header_panel">
        <h2>24-hour forecast</h2>
      </div>
    </div>
    <!-- Добавляем SVG для графика -->
    <svg width="100%" height="200" viewBox="0 0 500 1" class="graf_temp">
      <!-- Линия графика -->
      <polyline :points="linePoints" fill="none" stroke="red" stroke-width="1" />

      <!-- Точки на графике -->
      <circle
        v-for="(point, index) in points"
        :key="index"
        :cx="point.x"
        :cy="point.y"
        r="3"
        fill="white"
      />
    </svg>
    <div class="hours_block">
      <div class="block_hours" v-for="(temp, index) in temperatures" :key="index">
        <div class="number_temp" :style="{ marginBottom: computedMarginBottom(index) }">
          <h2 ref="tempHeader">{{ temp }}</h2>
          <span>°</span>
        </div>
        <IconRainCloud class="weather_icon" />
        <div class="wind_speed">
          <h2>{{ windSpeeds[index] }} km/h</h2>
        </div>
        <h2>{{ times[index] }}</h2>
      </div>
    </div>
  </div>
</template>

<style scoped>
.panel_info_forecast {
  line-height: 3vh;
  border-radius: 3vh;
  padding-top: 0.5vh;
  background: var(--color-back-panel);
  margin-top: 2vh;
  display: flex;
  align-items: flex-start;
  flex-direction: column;
}

.panel_info_forecast_header {
  width: 100%;
  grid-gap: 5px;
  margin-top: 1vh;
  padding-left: 6vw;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.header_panel {
  display: flex;
  align-items: center;
  grid-gap: 10px;
}

.hours_block {
  margin-bottom: 0.2vh;
  line-height: 4vh;
  display: flex;
  align-items: flex-end;
  flex-direction: row;
  width: 100%;
  justify-content: center;
}

.block_hours {
  line-height: 3vh;
  display: flex;
  align-items: center;
  flex-direction: column;
  width: 100%;
}

.block_hours h2 {
  margin-top: -0.5vh;
  font-size: 1vh;
}

.wind_speed {
  display: flex;
  align-items: center;
  grid-gap: 2vw;
}

.wind_speed h2,
span {
  margin-top: 0.5vh;
  font-size: 1.5vh;
}

.number_temp {
  display: flex;
  flex-direction: row;
  align-items: baseline;
}

.weather_icon {
  height: 3vh;
}

.graf_temp {
  margin-bottom: -90px;
  width: 100%;
  height: 86px;
}

@media (max-width: 392px) {
  .panel_info_forecast {
    font-size: 1.4vh;
  }

  .weather_icon {
    height: 2.5vh;
  }

  .block_hours h2 {
    font-size: 1.3vh;
  }

  .wind_speed h2,
  span {
    font-size: 1.3vh;
  }
}
</style>
