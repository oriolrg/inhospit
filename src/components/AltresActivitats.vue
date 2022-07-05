<template>
  <div :class="{ 'bg-blau': !nightMode, 'bg-dark': nightMode }" class="p-st">
    <div class="container py-4 bg-verd">
      <div
        class="text-center"
        data-aos="fade"
        data-aos-once="true"
        data-aos-duration="1000"
      >
        <span id="Altres activitats"
          class="title text-center"
          :class="{ pgray: !nightMode, 'text-light': nightMode }"
          >Altres Activitats</span>
      </div>
      
      
      <hr
        width="50%"
        :class="{ pgray: !nightMode, 'bg-secondary': nightMode }"
      />
      <br />
      <div class="row">
        <div  class="col-sm-4">
          <a :href="altresActivitats[1].web" v-tooltip.bottom="'Altres Activitats'" target="_blank">
            <div class="bg-div">
              <img class="imatge" :src="altresActivitats[1].img" />
            </div>
          </a>
          <div class="title2 pt-2">{{ altresActivitats[1].description }}</div>
        </div>
        <div  class="col-sm-4">
          <a :href="altresActivitats[2].web" v-tooltip.bottom="'Altres Activitats'" target="_blank">
            <div class="bg-div">
              <img class="imatge" :src="altresActivitats[2].img" />
            </div>
          </a>
          <div class="title2 pt-2">{{ altresActivitats[2].description }}</div>
        </div>
        <div  class="col-sm-4">
          <a :href="altresActivitats[3].web" v-tooltip.bottom="'Altres Activitats'" target="_blank">
            <div class="bg-div">
              <img class="imatge" :src="altresActivitats[3].img" />
            </div>
          </a>
          <div class="title2 pt-2">{{ altresActivitats[3].description }}</div>
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
      sortidors: info.demati[1],
      altresActivitats: info.demati,
      tallers: info.demati[3],
    };
  },
};
</script>

<style scoped>
.imatge{
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
</style>
