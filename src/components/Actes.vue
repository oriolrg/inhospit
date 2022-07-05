<template>
  <div
    class=" p-st bg-blau"
    :class="{
      'bg-light': !nightMode,
      'bg-dark2': nightMode,
      'text-light': nightMode,
    }"
  >
    <div class="container bg-groc">
      <div
        class="text-center"
        data-aos="fade"
        data-aos-once="true"
        data-aos-duration="1000"
      >
        <span
          class="title text-center"
          :class="{ pgray: !nightMode, 'text-light': nightMode }"
          >Actes Inhòspit 2022 Guixers</span
        >
      </div>
      <hr
        width="50%"
        :class="{ pgray: !nightMode, 'bg-secondary': nightMode }"
      />
      <div class="row">
        <div class="col-xl-6 col-bg-6 col-md-6 col-sm-12">
          <Timeline :data="demati" :nightMode="nightMode" class="bg-blau"/>
        </div>
        <div class="col-xl-6 col-bg-6 col-md-6 col-sm-12">
          <Timeline :data="tarda" :nightMode="nightMode"  class="bg-blau"/>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import Timeline from "./helpers/Timeline";
import info from "../../info";

export default {
  name: "Actes",
  components: {
    Timeline,
  },
  props: {
    nightMode: {
      type: Boolean,
    },
  },
  data() {
    return {
      demati: {
        title: "Tarda",
        data: info.demati,
      },
      tarda: {
        title: "Vespre",
        data: info.tarda,
      },
    };
  },
};
</script>

<style scoped>
.bg-groc{
  background-color:#F4C567 !important;
}
.bg-blau{
  background-color:#84a3dc !important;
}
.bg-verd{
  background-color:#74af6f !important;
}
.title {
  font-size: 30px;
  font-weight: 500;
}
</style>
