<template>
  <div :class="{ 'bg-blau': !nightMode, 'bg-dark': nightMode }" class="p-st">
    <div class="container py-4 bg-groc">
      <div
        class="text-center"
        data-aos="fade"
        data-aos-once="true"
        data-aos-duration="1000"
      >
        <span :id="musica.name"
          class="title text-center"
          :class="{ pgray: !nightMode, 'text-light': nightMode }"
          >Música</span
        >
      </div>
      <hr
        width="50%"
        :class="{ pgray: !nightMode, 'bg-secondary': nightMode }"
      />
      <div class="row">
        <div v-for="(music) in musics"
          :key="music.name" class="col-sm-4"
          data-aos="fade-up"
          data-aos-offset="10"
          data-aos-delay="30"
          :style="{ 'transition-delay': idx / 4.2 + 's' }"
          data-aos-duration="500"
          data-aos-easing="ease-in-out"
          data-aos-mirror="true"
          data-aos-once="true">
          <div class="card bg-blau">
            <img class="card-img-top" :src="music.img" :alt="music.name">
            <div class="card-body">
              <h5 class="card-title">{{ music.name }}</h5>
              <p class="card-text">{{ music.descripcio }}</p>
              <a :href="music.escolta" class="btn btn-primary" target="_blank">Escolta'l</a>
            </div>
          </div>
        </div>
      </div>
        
    
    </div>
  </div>
</template>


<script>
import info from "../../info";
import Card from "./helpers/Card";

export default {
  name: "Colaboradors",
  props: {
    nightMode: {
      type: Boolean,
    },
  },
  components: {
    Card,
  },
  data() {
    return {
      organitzadors: info.organitza,
      musics: info.musics,
      musica: info.tarda[1],
    };
  },
};
</script>

<style scoped>
.card-img-top{
  width: 100%;
}
.col-sm-4{
  margin-bottom: 12px;
}
.title {
  font-size: 30px;
  font-weight: 500;
}
.title1 {
  font-size: 24px;
  font-weight: 400;
}
.bg-blau{
  background-color: #84a3dc !important;
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
</style>
