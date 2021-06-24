<template>
  <div
    :class="[scrollPosition > 70 ? 'top' : 'top hide']"
    @click="scrollTopTop"
  >
    <svg class="top--icon">
      <use xlink:href="../../assets/sprite.svg#icon-keyboard_arrow_up"></use>
    </svg>
  </div>
</template>

<script>
export default {
  data() {
    return {
      scrollPosition: 0,
    };
  },
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY;
    },
    scrollTopTop() {
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    },
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
};
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.top {
  position: fixed;
  bottom: 3rem;
  right: 3rem;
  width: 2.2rem;
  height: 2.2rem;
  background-color: $secondary-color;
  //padding: 0.5rem 0.6rem;
  border-radius: 8px;
  cursor: pointer;
  border-bottom: 3px solid $third-color;
  display: flex;
  justify-content: center;
  align-items: center;

  .top--icon {
    width: 1.5rem;
    height: 1.5rem;
    fill: white;
  }
}

.top.hide {
  display: none;
}
</style>