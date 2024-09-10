<script setup lang="ts">
import IconCalendar from './icons/IconCalendar.vue'
import IconPolygon from './icons/IconPolygon.vue'
import IconRainCloud from './icons/weather/IconRainCloud.vue'
</script>
<template>
  <div class="panel_info">
    <div class="panel_info_header">
      <div class="header_panel">
        <IconCalendar class="icon_calendar" />
        <h2>5-day forecast</h2>
      </div>

      <div class="more_block">
        <h2>More</h2>
        <IconPolygon />
      </div>
    </div>
    <div class="days_block">
      <div class="block_day">
        <h2>Today</h2>
        <div class="temp_max_min">
          <IconRainCloud class="weather_icon" />
          <h2>50°</h2>
          <div class="back_temp">
            <div class="temp_panel"></div>
          </div>
          <h2>68°</h2>
        </div>
      </div>
      <div class="block_day">
        <h2>Tomorrow</h2>
        <div class="temp_max_min">
          <IconRainCloud class="weather_icon" />
          <h2>50°</h2>
          <div class="back_temp">
            <div class="temp_panel"></div>
          </div>
          <h2>68°</h2>
        </div>
      </div>
      <div class="block_day">
        <h2>Sat</h2>
        <div class="temp_max_min">
          <IconRainCloud class="weather_icon" />
          <h2>50°</h2>
          <div class="back_temp">
            <div class="temp_panel"></div>
          </div>
          <h2>68°</h2>
        </div>
      </div>
    </div>
    <button class="day5_btn jura-normal">5-day forecast</button>
  </div>
</template>
<style scoped>
.panel_info {
  line-height: 3vh;
  border-radius: 3vh;
  padding-left: 6vw;
  padding-right: 6vw;
  padding-top: 0.5vh;
  padding-bottom: 1vh;
  background: var(--color-back-panel);
  margin-top: 2vh;
  display: flex;
  align-items: flex-start;
  flex-direction: column;
  font-size: 1.7vh;
}

.panel_info_header {
  width: 100%;
  grid-gap: 5px;
  margin-top: 1vh;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.more_block,
.header_panel {
  display: flex;
  align-items: center;
  grid-gap: 10px;
}

.days_block {
  margin-top: 1.5vh;
  margin-bottom: 1.5vh;
  line-height: 3vh;
  display: flex;
  align-items: flex-start;
  flex-direction: column;
  width: 100%;
}

.icon_calendar {
  height: 4vh;
}

.block_day {
  margin-top: 1vh;
  margin-bottom: 2vh;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-direction: row;
  padding-bottom: 3vh; /* Отступы внутри блока для визуального оформления */
  border-bottom: 1px solid white; /* Белая полоса под каждым блоком */
}

.block_day h2 {
  font-size: 3vh;
}

.block_day:last-child {
  padding-bottom: 0; /* Убираем нижний отступ у последнего элемента */
  border-bottom: none; /* Убираем полосу под последним элементом */
  margin-bottom: 0.5vh;
}

.temp_max_min {
  display: flex;
  align-items: center;
  grid-gap: 2vw;
}

.temp_max_min h2 {
  font-size: 1.7vh;
}

.back_temp {
  border-radius: 30px;
  width: 16vw;
  height: 0.7vh;
  background: var(--color-temperature-gradient-back-panel);
}

.temp_panel {
  border-radius: 30px;
  height: 100%;
  width: 50%;
  margin-left: 0vw;
  background: var(--color-temperature-gradient);
}

.weather_icon {
  height: 2vh;
  margin-right: 5vw;
}

.day5_btn {
  background: var(--color-button-get-5-day);
  color: var(--color-font-white);
  margin-top: 1vh;
  margin-bottom: 1vh;
  width: 100%;
  font-size: 2.5vh;
  border: 0;
  border-radius: 30px;
  height: 5vh;
}

@media (max-width: 392px) {
  .panel_info {
    font-size: 1.4vh;
  }

  .day5_btn {
    font-size: 2vh;
  }

  .weather_icon {
    height: 2vh;
  }

  .block_day h2 {
    font-size: 2vh;
  }

  .temp_max_min h2 {
    font-size: 1.7vh;
  }
}
</style>
