<template>
  <section class="social">
    <div class="social__block" v-for="(social, index) in socials" :key="index">
      <svg class="social__block__icon">
        <use
          :xlink:href="require('@/assets/sprite.svg') + `#${social.icon}`"
        ></use>
      </svg>
      <p class="social__block__number">{{ social.number }}</p>
      <p class="social__block__detail">{{ social.text }}</p>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      socials: [
        { icon: "icon-group", number: "218889", text: "Project Done" },
        { icon: "icon-cloud-download", number: "98889", text: "Downloads" },
        {
          icon: "icon-facebook-official",
          number: "24640",
          text: "Sales in 2017",
        },
        { icon: "icon-twitter", number: "62504", text: "Happy Clients" },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.social {
  height: 20rem;
  background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
    url("../../assets/img/panorama.png");
  background-position: center;
  background-size: cover;

  display: grid;
  justify-items: center;
  align-items: center;
  grid-template-columns: repeat(4, 1fr);
  grid-column-gap: 2rem;
  grid-row-gap: 10px;

  @media only screen and (max-width: 1024px) {
    grid-template-columns: repeat(2, 1fr);
  }

  &__block {
    display: flex;
    flex-direction: column;
    align-items: center;

    &__icon {
      fill: $primary-color;
      width: 3rem;
      height: 3rem;
      margin-bottom: 1rem;
    }

    &__number {
      color: white;
      font-size: 1.4rem;
      font-weight: 900;
    }

    &__detail {
      color: white;
      font-size: 1.2rem;
    }
  }
}
</style>