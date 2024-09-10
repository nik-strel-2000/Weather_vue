<script setup></script>
<template>
  <div class="container">
    <img class="cloud" style="top: 50px; right: -17vh" src="../assets/Cloud.png" alt="" />
    <img class="cloud" style="top: 210px; right: 20vw" src="../assets/Cloud.png" alt="" />
  </div>
</template>

<style scoped>
.container {
  position: absolute;
  width: 100%;
  height: 100vh;
  overflow: hidden;
  z-index: -2;
}

.cloud {
  position: absolute;
  height: 25vh;
  /* Убедитесь, что z-index положительный */
}

img {
  position: absolute;
  height: 25vh;
  /* Убедитесь, что z-index достаточно высок для отображения поверх других элементов */
}
</style>
