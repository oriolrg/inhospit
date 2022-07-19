<template>
  <div id="app" :class="{ 'text-dark': !nightMode, 'text-light': nightMode }">
  
    <div class="parent">
      <Carrega v-if="isLoading"></Carrega>
      <div v-else>
        <!--<ContaEndarrere :nightMode="nightMode" />-->
        <ModalPopup :nightMode="nightMode" />
        <Home :nightMode="nightMode" />
        <Actes id="actes" :nightMode="nightMode" />
        <TaulaRodona :nightMode="nightMode" />
        <Tast :nightMode="nightMode" />
        <Sopar id="Sopar" :nightMode="nightMode" />
        <Musica id="musica" :nightMode="nightMode" />
        <AltresActivitats id="musica" :nightMode="nightMode" />
        <Organitza id="organitza" :nightMode="nightMode" />
        <Colaboradors id="colaboradors" :nightMode="nightMode" />
        <ComArribar id="organitza" :nightMode="nightMode" />
        <Footer :nightMode="nightMode" />
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Home from "./components/Home";
import Actes from "./components/Actes";
import Colaboradors from "./components/Colaboradors";
import Organitza from "./components/Organitza";
import Footer from "./components/Footer";
import Carrega from "./components/Carrega";
import TaulaRodona from "./components/TaulaRodona";
import Tast from "./components/Tast";
import Musica from "./components/Musica";
import Sopar from "./components/Sopar";
import ComArribar from "./components/ComArribar";
//import ContaEndarrere  from "./components/ContaEndarrere";
import ModalPopup  from "./components/ModalPopup";
import AltresActivitats from "./components/AltresActivitats"

import info from "../info";

export default {
  name: "App",
  components: {
    Navbar,
    Home,
    Actes,
    Colaboradors,
    Organitza,
    Footer,
    Carrega,
    TaulaRodona,
    ComArribar,
    Tast,
    Musica,
    Sopar,
    AltresActivitats,
    ModalPopup,
  },
  data() {
    return {
      nightMode: false,
      config: info.config,
      isLoading: true,
    };
  },
  
  created() {
    if (this.config.use_cookies) {
      this.nightMode = this.$cookie.get("nightMode") === "true" ? true : false;
    }
  },
  mounted() {
    ["actes",  "colaboradors", "portfolio"].forEach((l) => {
      if (window.location.href.includes(l)) {
        var elementPosition = document.getElementById(l).offsetTop;
        window.scrollTo({ top: elementPosition - 35, behavior: "smooth" });
      }
    });
    setTimeout(() => {
      this.isLoading = false;
    }, 2500);
  },
  methods: {
    switchMode(mode) {
      if (this.config.use_cookies) {
        this.$cookie.set("nightMode", mode);
      }
      this.nightMode = mode;
    },
    scrollTo(ele) {
      if (ele == "home") {
        this.$router.push(`/`);
        window.scrollTo({ top: -80, behavior: "smooth" });
      } else {
        var elementPosition = document.getElementById(ele).offsetTop;
        window.scrollTo({ top: elementPosition - 35, behavior: "smooth" });
        if (this.$router.history.current.path !== `/${ele}`)
          this.$router.push(`/${ele}`);
      }
    },
  },
};
</script>

<style>
body {
    margin: 0;
    padding: 0;
}
#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  width: 100%;
  top: 0px;
  position: absolute;
}
.container{
  max-width: 98%;
  position: relative;
}

.descripcio-text{
  font-size: 18px;
  font-weight:300;
}
@media screen and (max-width: 580px) {
  #app {
    width: fit-content;
  }
}

.parent {
  position: relative;
  
}

.pgray {
  color: #535a5e;
}

.pblue {
  color: #669db3ff;
}
.bg-groc{
  background-color:#f4c567 !important;
}
.bg-blau{
  background-color:#82B7D8 !important;
}
.bg-verd{
  background-color:#89CC89 !important;
}
.bg-dark2 {
  background-color: #262c30 !important;
}

.text-light {
  color: #d3d2d2 !important;
}

.p-st {
  transition: all 0.5s !important;
}

/* To set scrollbar width */
::-webkit-scrollbar {
  width: 5px;
}

/* Track */
::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 9px;
  border: 2px solid white; /* Use your background color instead of White */
  background-clip: content-box;
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #888;
  border-radius: 9px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555;
}

.tooltip {
  display: block !important;
  z-index: 10000;
}

.tooltip .tooltip-inner {
  background: rgb(212, 149, 97);
  color: white;
  border-radius: 8px;
  font-size: 10px;
  /* padding: 5px 10px 4px; */
}

.tooltip .tooltip-arrow {
  width: 0;
  height: 0;
  border-style: solid;
  position: absolute;
  margin: 5px;
  border-color: rgb(212, 149, 97);
  z-index: 1;
}

.tooltip[x-placement^="top"] {
  margin-bottom: 5px;
}

.tooltip[x-placement^="top"] .tooltip-arrow {
  border-width: 5px 5px 0 5px;
  border-left-color: transparent !important;
  border-right-color: transparent !important;
  border-bottom-color: transparent !important;
  bottom: -5px;
  left: calc(50% - 5px);
  margin-top: 0;
  margin-bottom: 0;
}

.tooltip[x-placement^="bottom"] {
  margin-top: 10px;
}

.tooltip[x-placement^="bottom"] .tooltip-arrow {
  border-width: 0 5px 5px 5px;
  border-left-color: transparent !important;
  border-right-color: transparent !important;
  border-top-color: transparent !important;
  top: -5px;
  left: calc(50% - 5px);
  margin-top: 0;
  margin-bottom: 0;
}

.tooltip[x-placement^="right"] {
  margin-left: 5px;
}

.tooltip[x-placement^="right"] .tooltip-arrow {
  border-width: 5px 5px 5px 0;
  border-left-color: transparent !important;
  border-top-color: transparent !important;
  border-bottom-color: transparent !important;
  left: -5px;
  top: calc(50% - 5px);
  margin-left: 0;
  margin-right: 0;
}

.tooltip[x-placement^="left"] {
  margin-right: 5px;
}

.tooltip[x-placement^="left"] .tooltip-arrow {
  border-width: 5px 0 5px 5px;
  border-top-color: transparent !important;
  border-right-color: transparent !important;
  border-bottom-color: transparent !important;
  right: -5px;
  top: calc(50% - 5px);
  margin-left: 0;
  margin-right: 0;
}

.tooltip.popover .popover-inner {
  background: #f9f9f9;
  color: black;
  padding: 24px;
  border-radius: 5px;
  box-shadow: 0 5px 30px rgba(black, 0.1);
}

.tooltip.popover .popover-arrow {
  border-color: #f9f9f9;
}

.tooltip[aria-hidden="true"] {
  visibility: hidden;
  opacity: 0;
  transition: opacity 0.5s, visibility 0.5s;
}

.tooltip[aria-hidden="false"] {
  visibility: visible;
  opacity: 1;
  transition: opacity 0.5s;
}
</style>
