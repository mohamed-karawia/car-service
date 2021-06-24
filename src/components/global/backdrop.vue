<template>
  <div>
    <div class="backdrop" @click="toggleBackdrop"></div>
    <div class="backdrop__container">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },

  methods: {
    toggleBackdrop() {
      this.$emit("hideBackdrop");
    },
  },
  computed: {},
};
</script>

<style lang="scss" scoped>
.backdrop {
  width: 100%;
  height: 100%;
  position: fixed;
  z-index: 900;
  left: 0;
  top: 0;
  background-color: rgba(0, 0, 0, 0.5);

  &__container {
    position: fixed;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    width: 90vw;
    max-width: 45rem;
    z-index: 999;
  }
}
</style>