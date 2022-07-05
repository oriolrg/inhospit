<template>
<div :class="{ 'bg-blau': !nightMode, 'bg-dark': nightMode }" class="p-st">
<section class="ComArribar" id="ComArribar">
  <div class="container py-4 bg-groc">
        <div
          class="text-center"
          data-aos="fade"
          data-aos-once="true"
          data-aos-duration="1000"
        >
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2958.8347156865316!2d1.662137919289333!3d42.13242152242186!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x12a5bb4555555555%3A0x3a49db3fabf59a54!2sAjuntament%20de%20Guixers!5e0!3m2!1sca!2ses!4v1655985985496!5m2!1sca!2ses" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
        </div>
  </div>
</section>
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
      tast: info.demati,
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
.card{
  margin: 1rem;
  padding: 1rem;
  text-align: center;
  height: 26rem;
}
.titol{
  margin-bottom: 1rem;
}
.logoCol{
  margin-bottom: 2rem;
}
.logoColCervesa{
  width: 100%;
}
</style>
