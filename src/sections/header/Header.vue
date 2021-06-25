<template>
  <header class="header" id="header">
    <div class="header--details">
      <h2>Professional repair of cars of all brands.</h2>
      <p>
        The largest <span>autotechnical center</span> in
        <span>2350</span> cities with modern equipment and
        <span>qualified</span> personnel.
      </p>
      <button @click="showBackdrop = true">online order</button>
    </div>
    <Content />
    <Backdrop v-if="showBackdrop" @hideBackdrop="showBackdrop = false"
      ><Form @hideBackdrop="showBackdrop = false"
    /></Backdrop>
  </header>
</template>

<script>
import Content from "../../components/Header/content.vue";
import Backdrop from "../../components/global/backdrop.vue";
import Form from "../../components/global/form.vue";

export default {
  data() {
    return {
      showBackdrop: false,
    };
  },
  components: {
    Content,
    Backdrop,
    Form,
  },
};
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.header {
  width: 100%;
  min-height: 120vh;
  background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
    url("../../assets/img/b1.jpg");
  background-position: center;
  background-size: cover;

  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 0 2.8rem;

  position: relative;

  @media only screen and (max-width: 830px) {
    justify-content: center;
  }

    @media only screen and (max-width: 360px) {
    padding: 0 1rem;
    //justify-content: start;
  }

  &--details {
    color: #ffff;
    width: 50%;
    margin-top: 10rem;

    @media only screen and (max-width: 830px) {
      width: 100%;
    }

    & > * {
      margin-bottom: 2rem;
    }

    h2 {
      font-size: 3.5rem;
      font-weight: 900;
      line-height: 4rem;
      text-transform: capitalize;
    }

    p {
      font-size: 1.2rem;
      font-weight: 300;

      span {
        font-weight: 700;
      }
    }

    button {
      font-size: 1.2rem;
      font-weight: 300;
      border: none;
      background-color: $secondary-color;
      color: white;
      padding: 0.5rem 0.6rem;
      border-radius: 10px;
      cursor: pointer;
      text-transform: capitalize;
      border-bottom: 3px solid $third-color;
      transition: all 0.2s;

      &:hover {
        background-color: $primary-color;
        scale: 1.1;
        box-shadow: 10px 10px 10px -5px rgba(0, 0, 0, 0.281);
        -webkit-box-shadow: 10px 10px 10px -5px rgba(0, 0, 0, 0.281);
        -moz-box-shadow: 10px 10px 10px -5px rgba(0, 0, 0, 0.281);
      }
    }
  }
}
</style>