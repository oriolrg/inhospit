<template>
  <div :class="{ 'bg-blau': !nightMode, 'bg-dark': nightMode }" class="p-st">
    <div class="container py-4 bg-groc">
      <div
        class="text-center"
        data-aos="fade"
        data-aos-once="true"
        data-aos-duration="1000"
      >
        <span :id="tast.name"
          class="title text-center"
          :class="{ pgray: !nightMode, 'text-light': nightMode }"
          >{{tast.name}}</span>
        <div class="bg-div">{{tast.place}}</div>
        <div class="title2 col-sm-12">
          <div class="bg-div column">
            <a class="imgGran" :href="tast.url">
              Compra el Tiquet
              <svg xmlns="http://www.w3.org/2000/svg" width="46" height="46" fill="currentColor" class="bi bi-ticket-detailed" viewBox="0 0 16 16">
                  <path d="M4 5.5a.5.5 0 0 1 .5-.5h7a.5.5 0 0 1 0 1h-7a.5.5 0 0 1-.5-.5Zm0 5a.5.5 0 0 1 .5-.5h7a.5.5 0 0 1 0 1h-7a.5.5 0 0 1-.5-.5ZM5 7a1 1 0 0 0 0 2h6a1 1 0 1 0 0-2H5Z"/>
                  <path d="M0 4.5A1.5 1.5 0 0 1 1.5 3h13A1.5 1.5 0 0 1 16 4.5V6a.5.5 0 0 1-.5.5 1.5 1.5 0 0 0 0 3 .5.5 0 0 1 .5.5v1.5a1.5 1.5 0 0 1-1.5 1.5h-13A1.5 1.5 0 0 1 0 11.5V10a.5.5 0 0 1 .5-.5 1.5 1.5 0 1 0 0-3A.5.5 0 0 1 0 6V4.5ZM1.5 4a.5.5 0 0 0-.5.5v1.05a2.5 2.5 0 0 1 0 4.9v1.05a.5.5 0 0 0 .5.5h13a.5.5 0 0 0 .5-.5v-1.05a2.5 2.5 0 0 1 0-4.9V4.5a.5.5 0 0 0-.5-.5h-13Z"/>
              </svg>
            </a>
          </div>
        </div>
      </div>
      <hr
        width="50%"
        :class="{ pgray: !nightMode, 'bg-secondary': nightMode }"
      />
      <br />
        <div class="row">          
          <div v-for="(cervesa) in tast.cerveses" :key="cervesa"  class="title2 col-sm-4"
          data-aos="fade-up"
          data-aos-offset="10"
          data-aos-delay="30"
          :style="{ 'transition-delay': idx / 4.2 + 's' }"
          data-aos-duration="500"
          data-aos-easing="ease-in-out"
          data-aos-mirror="true"
          data-aos-once="true">
            <div class="card bg-blau">
              <h2 class="titol">{{cervesa.nom}}</h2>
              <a  :href="cervesa.web"  v-tooltip.bottom="cervesa.descripcio" target="_blank"><div class="bg-div"><img class="logoColCervesa" :src="cervesa.imatge" /></div></a>
              <p class="descripcio-text">{{cervesa.descripcio}}</p>
            </div>
          </div>
        </div>
        <div class="row"> 
          <div v-for="(producte) in tast.productes" :key="producte" class="title2 col-sm-4"
          data-aos="fade-up"
          data-aos-offset="10"
          data-aos-delay="30"
          :style="{ 'transition-delay': idx / 4.2 + 's' }"
          data-aos-duration="500"
          data-aos-easing="ease-in-out"
          data-aos-mirror="true"
          data-aos-once="true">
            <div class="card bg-blau">
              <h2 class="titol">{{producte.nom}}</h2>
              <a  :href="producte.web" v-tooltip.bottom="producte.descripcio" target="_blank">
                <div class="bg-div"><img class="logoCol" :src="producte.imatge" /></div>
              </a>
              <p class="descripcio-text">{{producte.descripcio}}</p>
            </div>
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
      tast: info.demati[4],
    };
  },
};
</script>

<style scoped>
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
  max-width: 15em;
}
.card{
  margin: 1rem;
  padding: 1rem;
  text-align: center;
  height: 39rem;
}
.titol{
  margin-bottom: 1rem;
}
.logoCol{
  margin-bottom: 2rem;
}
.logoColCervesa{
  width: 20rem;
}

.imgGran{
  text-decoration: none;
}
</style>
