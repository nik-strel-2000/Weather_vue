<script setup lang="ts">


</script>

<template>
  <div class="panel_uv">
    <h1 class="header_panel_uv">UV</h1>
    <h2 class="subheader_panel_uv">Moderate</h2>
    <div class="panel_index_uv">
      <div class="panel_index_context_uv">
        <p>5</p>
        <img class="img_uv" src="../components/icons/UV-index.png" alt="UV index"/>
      </div>
    </div>
  </div>
</template>

<style scoped>
.panel_uv{
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
.header_panel_uv{
  color: var(--color-font-gray);
  font-size: 2vh ;
}
.subheader_panel_uv {
  font-size: 2.2vh;
}
.panel_index_uv{
  width: 100%;
  display: flex;
  align-items: center;
  flex-direction: row;
  justify-content: flex-end;
  padding-right: 8vw;
}
.panel_index_context_uv{
  height: 8vh;
  position: relative;
  margin-top: 0.5vh;
}
.panel_index_context_uv p{
  font-size: 3vh;
  position: absolute;
  top: 50%;
  left: 50%;
  margin-right: -50%;
  transform: translate(-50%, -50%)
}
.img_uv{
  height: 100%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}


</style>