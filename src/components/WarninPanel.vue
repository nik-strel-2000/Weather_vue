<script setup lang="ts">
import IconWarning from './icons/IconWarning.vue'
</script>
<template>
  <div class="panel_warning">
    <div class="panel_warning_header">
      <IconWarning class="icon_warning" />
      <h2>Yellow fog warning</h2>
    </div>
    <h3>
      In the central and southern regions of the Krasnoyarsk region at night and in the morning in
      some places fog is expected, in the central and southern regions hot weather, air temperature
      during the day in some places +30,+32 °, in the central regions in some places will remain
      high fire danger class IV.
    </h3>
  </div>
</template>
<style scoped>
.panel_warning {
  line-height: 4vh;
  width: 90vw;
  border-radius: 3vh;
  padding-left: 6vw;
  padding-right: 6vw;
  padding-top: 0.5vh;
  padding-bottom: 1vh;
  background: var(--color-back-panel);
  margin-top: 6vh;
  display: flex;
  align-items: flex-start;
  flex-direction: column;
  font-size: 1.7vh;
}

.panel_warning h3 {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  width: 100%;
}

.panel_warning_header {
  grid-gap: 5px;

  display: flex;
  align-items: center;
}

.icon_warning {
  height: 2vh;
}
</style>
