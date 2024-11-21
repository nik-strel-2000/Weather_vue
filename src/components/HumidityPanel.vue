<script setup lang="ts">


import IconBlob from "@/components/icons/IconBlob.vue";
import IconProgressHumidity from "@/components/icons/IconProgressHumidity.vue";
</script>

<template>
  <div class="panel_humidity">
    <h1 class="header_panel_humidity">Humidity</h1>
    <h2 class="subheader_panel_humidity">40%</h2>
    <div class="panel_index_humidity">
      <div class="panel_index_context_humidity">
        <IconBlob class="centre_item"/>
        <IconProgressHumidity class="img_humidity"/>
      </div>
    </div>
  </div>
</template>

<style scoped>
.panel_humidity{
  line-height: 3vh;
  border-radius: 3vh;
  margin-top: 2vh;
  padding: 0.5vh 5vw 1.5vh;
  background: var(--color-back-panel);
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 43vw;
  flex-wrap: nowrap;
}
.header_panel_humidity{
  color: var(--color-font-gray);
  font-size: 2vh ;
}
.subheader_panel_humidity {
  font-size: 2.2vh;
}
.panel_index_humidity{
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: row;
  justify-content: flex-end;
  padding-right: 8vw;
}
.panel_index_context_humidity{
  height: 8vh;
  position: relative;
  margin-top: 0.5vh;
}
.centre_item{
  height: 3vh;
  position: absolute;
  top: 50%;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%)
}
.img_humidity{
  height: 100%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}


</style>