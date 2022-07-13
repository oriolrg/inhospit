<template>
  <div :class="{ 'bg-blau': !nightMode, 'bg-dark': nightMode }" class="p-st">
    <div class="container py-4 bg-groc">
      <div
        class="text-center"
        data-aos="fade"
        data-aos-once="true"
        data-aos-duration="1000"
      >
        <span
          class="title text-center"
          :class="{ pgray: !nightMode, 'text-light': nightMode }"
          >Organitza</span
        >
      </div>
      <hr
        width="50%"
        :class="{ pgray: !nightMode, 'bg-secondary': nightMode }"
      />
      <br />
      <div class="row">
        <div
          class="col-xl-12 col-bg-12 col-md-12 col-sm-12 text-center pb-5 px-4"
          v-for="(organitza, idx) in organitzadors"
          :key="organitza.title"
          data-aos="fade-up"
          data-aos-offset="10"
          data-aos-delay="30"
          :style="{ 'transition-delay': idx / 4.2 + 's' }"
          data-aos-duration="500"
          data-aos-easing="ease-in-out"
          data-aos-mirror="true"
          data-aos-once="true"
        >
          <a :href="organitza.web" v-tooltip.bottom="organitza.title" target="_blank"><div class="bg-div"><img class="logoCol" :src="organitza.img" /></div></a>
          <div class="title2 pt-2">{{ organitza.title }}</div>
          <span class="title3">{{ organitza.info.join(", ") }}</span>
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
      organitzadors: info.organitza,
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
  max-width: 8em;
}
</style>
