<template>
  <div class="services--grid">
    <single-service
      v-for="(service, index) in services"
      :key="index"
      :service="service"
      @showBackdrop="showBackdrop = true"
    />
    <Backdrop v-if="showBackdrop" @hideBackdrop="toggleBackdrop"
      ><Form @hideBackdrop="showBackdrop = false"
    /></Backdrop>
  </div>
</template>

<script>
import Backdrop from "../../components/global/backdrop.vue";
import Form from "../../components/global/form.vue";

import singleService from "./singleService.vue";
import img1 from "../../assets/img/service2-1.jpg";
import img2 from "../../assets/img/service2-2.jpg";
import img3 from "../../assets/img/service2-3.jpg";
import img4 from "../../assets/img/service2-4.jpg";
import img5 from "../../assets/img/service2-5.jpg";
import img6 from "../../assets/img/service2-6.jpg";
import img7 from "../../assets/img/service2-7.jpg";
import img8 from "../../assets/img/service2-8.jpg";

export default {
  data() {
    return {
      showBackdrop: false,
      services: [
        { img: img1, text: "Technical service cars" },
        { img: img2, text: "Independent Expertise" },
        { img: img3, text: "Body repair of any complexity" },
        { img: img4, text: "Car painting service" },
        { img: img5, text: "Professional body polishing" },
        { img: img6, text: "Headlight Polishing" },
        { img: img7, text: "Repair electrical equipment" },
        { img: img8, text: "Overhaul of engines" },
      ],
    };
  },
  components: {
    singleService,
    Backdrop,
    Form,
  },
  methods: {
    toggleBackdrop() {
      this.showBackdrop = false;
    },
  },
};
</script>

<style lang="scss" scoped>
.services--grid {
  width: 100%;
  margin-top: 1.5rem;
  padding: 0 5rem;

  display: grid;
  grid-template-columns: repeat(4, minmax(15rem, 1fr));
  grid-column-gap: 2rem;
  grid-row-gap: 10px;

  @media only screen and (max-width: 1024px) {
    grid-template-columns: repeat(2, 1fr);
  }

  @media only screen and (max-width: 720px) {
    padding: 0 3rem;
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>