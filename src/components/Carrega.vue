<template>
  <div id="loading" class="bg-blau">
    <img src="../assets/logoInhospit.gif" style="height:50%"/>
  </div>
</template>

<script>
export default {
  name: "Carrega"
};
</script>
<style>
body {
    margin: 0;
    padding: 0;
    background-color: #74af6f !important;
}
#loading {
  position: absolute;
  z-index: 1000;
  background-color: white;
  height: 100vh;
  width: 100vw;
  text-align: center;
  line-height: 100vh;
}
.img {
  position: relative;
  margin: auto;
  margin-top: 20%;
}
</style>