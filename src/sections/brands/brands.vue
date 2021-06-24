<template>
  <section class="brands">
      <div class="brand--container" v-for="(i, index) in 12" :key="index">
          <img :src="require(`../../assets/img/brands-${i}.png`)" alt="">
      </div>
  </section>
</template>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.brands {
  width: 100%;
  background-color: $gray;

  padding: 5rem 3rem;

  display: grid;
  justify-items: center;
  grid-template-columns: repeat(6, 1fr);
  grid-row-gap: 2rem;

  @media only screen and (max-width: 900px) {
    padding: 6rem 0.5rem;
  grid-template-columns: repeat(4, 1fr);

  }

    @media only screen and (max-width: 500px) {
    padding: 6rem 0.5rem;
  grid-template-columns: repeat(2, 1fr);

  }

  .brand--container{
      width: 7rem;

      img{
          width: 100%;
      }
  }
}
</style>