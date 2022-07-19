<template>
  <div v-show="this.isModalVisible" class="modal-backdrop" @click="closeModal">
    <div class="modal">
      <section class="modal-body">
        <button
          type="button"
          class="btn-close"
          @click="closeModal"
        >
          x
        </button>
        <slot name="body">
          <div class="col-xl-12 col-bg-12 col-md-12 col-sm-12 text-center">
            <img class="headerimatge" :src="gracies" />
          </div>
        </slot>
       </section>

      <footer class="modal-footer">
        <slot name="footer" class="row">
          <div class="row">
            <div
              class="col-xl-4 col-bg-4 col-md-4 col-sm-12 text-center pb-5 px-4"
              
              :key="colaboradors[0].title"
              data-aos="fade-up"
              data-aos-offset="10"
              data-aos-delay="30"
              :style="{ 'transition-delay': idx / 4.2 + 's' }"
              data-aos-duration="500"
              data-aos-easing="ease-in-out"
              data-aos-mirror="true"
              data-aos-once="true"
            >
              <a  :href="colaboradors[0].web" v-tooltip.bottom="colaboradors[0].title" target="_blank"><div class="bg-div"><img class="logoCol" :src="colaboradors[0].img" :alt="colaboradors[0].title"/></div></a>
              <!--<div class="title2 pt-2">{{ colaborador.title }}</div>-->
              <span class="title3">{{ colaboradors[0].info.join(", ") }}</span>
            </div>
            <div
              class="col-xl-4 col-bg-4 col-md-4 col-sm-12 text-center pb-5 px-4"
              
              :key="colaboradors[7].title"
              data-aos="fade-up"
              data-aos-offset="10"
              data-aos-delay="30"
              :style="{ 'transition-delay': idx / 4.2 + 's' }"
              data-aos-duration="500"
              data-aos-easing="ease-in-out"
              data-aos-mirror="true"
              data-aos-once="true"
            >
              <a  :href="colaboradors[7].web" v-tooltip.bottom="colaboradors[7].title" target="_blank"><div class="bg-div"><img class="logoCol" :src="colaboradors[7].img" :alt="colaboradors[7].title"/></div></a>
              <!--<div class="title2 pt-2">{{ colaborador.title }}</div>-->
              <span class="title3">{{ colaboradors[7].info.join(", ") }}</span>
            </div>
            <div
              class="col-xl-4 col-bg-4 col-md-4 col-sm-12 text-center pb-5 px-4"
              
              :key="colaboradors[6].title"
              data-aos="fade-up"
              data-aos-offset="10"
              data-aos-delay="30"
              :style="{ 'transition-delay': idx / 4.2 + 's' }"
              data-aos-duration="500"
              data-aos-easing="ease-in-out"
              data-aos-mirror="true"
              data-aos-once="true"
            >
              <a  :href="colaboradors[6].web" v-tooltip.bottom="colaboradors[6].title" target="_blank"><div class="bg-div"><img class="logoCol" :src="colaboradors[6].img" :alt="colaboradors[6].title"/></div></a>
              <!--<div class="title2 pt-2">{{ colaborador.title }}</div>-->
              <span class="title3">{{ colaboradors[6].info.join(", ") }}</span>
            </div>
          </div>
        </slot>
      </footer>
    </div>
  </div>
</template>



<script>
import info from "../../info";
  export default {
    name: 'Modal',
    data() {
      return {
        isModalVisible: true,
        organitzadors: info.organitza,
        colaboradors: info.colaboradors,
        picture: info.flat_picture,
        gracies: info.gracies,
      };
    },
    methods: {
      closeModal() {
        this.isModalVisible = false;
      }
    },
  };
</script>


<style>
  .logoCol{
    width: 5rem;
  }
  .headerimatge{
    width: 25rem !important;
  }
  .modal-backdrop {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(0, 0, 0, 0.3);
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .modal {
    background: #f4c567 !important;
    box-shadow: 2px 2px 20px 1px;
    overflow-x: auto;
    display: flex;
    flex-direction: column;
  }

  .modal-header,
  .modal-footer {
    display: flex;
  }

  .modal-header {
    position: relative;
    border-bottom: 1px solid #eeeeee;
    color: #4AAE9B;
    justify-content: space-between;
  }

  .modal-footer {
    border-top: 1px solid #eeeeee;
    flex-direction: column;
    justify-content: flex-end;
  }

  .modal-body {
    position: relative;
    padding: 20px 10px;
  }

  .btn-close {
    position: absolute;
    top: 0;
    right: 0;
    border: none;
    font-size: 20px;
    padding: 10px;
    cursor: pointer;
    font-weight: bold;
    color: #4AAE9B;
    background: transparent;
  }

  .btn-green {
    color: white;
    background: #4AAE9B;
    border: 1px solid #4AAE9B;
    border-radius: 2px;
  }
</style>
