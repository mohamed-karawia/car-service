<template>
  <div
    @click="showBackdrop"
    class="service"
    :style="{ 'background-image': 'url(' + service.img + ')' }"
  >
    <div class="service__details">
      {{ service.text }}
    </div>
  </div>
</template>

<script>


export default {
    methods: {
      showBackdrop(){
        this.$emit('showBackdrop')
      }
    },
  props: {
    service: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.service {
  height: 15rem;
  background-size: cover;
  background-position: center;
  position: relative;
  cursor: pointer;

  &__details {
    position: absolute;
    top: 70%;
    padding: 0.5rem 0.5rem;
    background-color: rgba(0, 0, 0, 0.726);
    color: white;
    font-size: 1.2rem;
    font-weight: 600;
    border-right: 2px solid $primary-color;
  }

  @media only screen and (max-width: 720px) {
    height: 22rem;
  }
}
</style>