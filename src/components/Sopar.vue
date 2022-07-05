<template>
  <div :class="{ 'bg-blau': !nightMode, 'bg-dark': nightMode }" class="p-st">
    <div class="container py-4 bg-verd">
      <div
        class="text-center"
        data-aos="fade"
        data-aos-once="true"
        data-aos-duration="1000"
      >
        <span id="Sopar fera a l'ast"
          class="title text-center"
          :class="{ pgray: !nightMode, 'text-light': nightMode }"
          >Sopar fera a l'ast</span
        >
        <div class="row"> 
          <div class="title2 col-sm-6">
            <div class="bg-div column"><img class="imgGran" :src="img.img0" /></div>
          </div>
          <div class="title2 col-sm-6">
            <div class="bg-div column"><img class="imgGran" :src="img.img1" /></div>
            </div>
        </div>
        <div class="row"> 
          <div class="title2 col-sm-6">
            <div class="bg-div column">
              <a class="imgGran" :href="img.link0">
                Compra el Tiquet
                <svg xmlns="http://www.w3.org/2000/svg" width="46" height="46" fill="currentColor" class="bi bi-ticket-detailed" viewBox="0 0 16 16">
                    <path d="M4 5.5a.5.5 0 0 1 .5-.5h7a.5.5 0 0 1 0 1h-7a.5.5 0 0 1-.5-.5Zm0 5a.5.5 0 0 1 .5-.5h7a.5.5 0 0 1 0 1h-7a.5.5 0 0 1-.5-.5ZM5 7a1 1 0 0 0 0 2h6a1 1 0 1 0 0-2H5Z"/>
                    <path d="M0 4.5A1.5 1.5 0 0 1 1.5 3h13A1.5 1.5 0 0 1 16 4.5V6a.5.5 0 0 1-.5.5 1.5 1.5 0 0 0 0 3 .5.5 0 0 1 .5.5v1.5a1.5 1.5 0 0 1-1.5 1.5h-13A1.5 1.5 0 0 1 0 11.5V10a.5.5 0 0 1 .5-.5 1.5 1.5 0 1 0 0-3A.5.5 0 0 1 0 6V4.5ZM1.5 4a.5.5 0 0 0-.5.5v1.05a2.5 2.5 0 0 1 0 4.9v1.05a.5.5 0 0 0 .5.5h13a.5.5 0 0 0 .5-.5v-1.05a2.5 2.5 0 0 1 0-4.9V4.5a.5.5 0 0 0-.5-.5h-13Z"/>
                </svg>
              </a>
            </div>
          </div>
          <div class="title2 col-sm-6">
            <div class="bg-div column">
              <a class="imgGran" :href="img.link1">
                Compra el Tiquet
                <svg xmlns="http://www.w3.org/2000/svg" width="46" height="46" fill="currentColor" class="bi bi-ticket-detailed" viewBox="0 0 16 16">
                    <path d="M4 5.5a.5.5 0 0 1 .5-.5h7a.5.5 0 0 1 0 1h-7a.5.5 0 0 1-.5-.5Zm0 5a.5.5 0 0 1 .5-.5h7a.5.5 0 0 1 0 1h-7a.5.5 0 0 1-.5-.5ZM5 7a1 1 0 0 0 0 2h6a1 1 0 1 0 0-2H5Z"/>
                    <path d="M0 4.5A1.5 1.5 0 0 1 1.5 3h13A1.5 1.5 0 0 1 16 4.5V6a.5.5 0 0 1-.5.5 1.5 1.5 0 0 0 0 3 .5.5 0 0 1 .5.5v1.5a1.5 1.5 0 0 1-1.5 1.5h-13A1.5 1.5 0 0 1 0 11.5V10a.5.5 0 0 1 .5-.5 1.5 1.5 0 1 0 0-3A.5.5 0 0 1 0 6V4.5ZM1.5 4a.5.5 0 0 0-.5.5v1.05a2.5 2.5 0 0 1 0 4.9v1.05a.5.5 0 0 0 .5.5h13a.5.5 0 0 0 .5-.5v-1.05a2.5 2.5 0 0 1 0-4.9V4.5a.5.5 0 0 0-.5-.5h-13Z"/>
                </svg>
              </a>
            </div>
            </div>
        </div>
        
      </div>
      <hr
        width="50%"
        :class="{ pgray: !nightMode, 'bg-secondary': nightMode }"
      />
      <div class="row"> 
          <div class="title2 col-sm-6" v-for="(sopar) in sopars"
            :key="sopar.nom" style="margin:auto;text-align:center;">
            <h2>{{sopar.nom}}</h2>
            {{sopar.autor}}
            {{sopar.oferta}}
          </div>
      </div>
      </div>
      </div>
</template>


<script>
import info from "../../info";

export default {
  name: "Colaboradors",
  props: {
    nightMode: {
      type: Boolean,
    },
  },
  data() {
    return {
      sopars: info.sopars,
      musica: info.tarda[2],
      img: info.imgSopars,
    };
  },
};
</script>

<style scoped>
.imgGran{
  width: 25rem;
}
.title {
  font-size: 30px;
  font-weight: 500;
}
.title1 {
  font-size: 24px;
  font-weight: 400;
}

.title2 {
  font-size: 20px;
  font-weight: 500;
}

.title3 {
  font-size: 16px;
  font-weight: 400;
}

.fa {
  color: rgb(212, 149, 97);
  font-size: 40px;
  transition: all 0.5s;
}

.fas {
  color: rgb(212, 149, 97);
  font-size: 40px;
  /* font-weight: bold; */
  transition: all 0.5s;
}
.logoCol{
  max-width: 8em;
}

.imgGran{
  text-decoration: none;
}
</style>
