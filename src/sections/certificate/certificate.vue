<template>
  <section class="certificate">
    <p>Our company is the best because:</p>
    <div class="certificate__heading">
      <h2>Сertificate</h2>
    </div>
    <div class="certificate__container">
      <div class="certificate__container__img">
        <img src="../../assets/img/certificate2.png" alt="certificate" />
      </div>
      <div class="certificate__container__img">
        <img src="../../assets/img/certificate2.png" alt="certificate" />
      </div>
      <div class="certificate__container__img">
        <img src="../../assets/img/certificate2.png" alt="certificate" />
      </div>
      <div class="certificate__container__img">
        <img src="../../assets/img/certificate2.png" alt="certificate" />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.certificate {
  background-color: $gray;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  padding: 6rem 3rem;

  p {
    @include sectionP;
  }

  &__heading {
    @include sectionHeading;
  }

  &__container {
    margin-top: 3rem;
    width: 100%;

    display: grid;
    justify-items: center;
    grid-template-columns: repeat(4, 1fr);

    @media only screen and (max-width: 1040px){
        grid-template-columns: repeat(2, 1fr);
        grid-row-gap: 1rem;
    }

        @media only screen and (max-width: 600px){
        grid-template-columns: repeat(1, 1fr);
        grid-row-gap: 1rem;
    }

    &__img {
      border: 8px solid #565656;
      box-shadow: 10px 10px 10px -5px rgba(0, 0, 0, 0.281);
      -webkit-box-shadow: 10px 10px 10px -5px rgba(0, 0, 0, 0.281);
      -moz-box-shadow: 10px 10px 10px -5px rgba(0, 0, 0, 0.281);
      padding: 1rem;
    }
  }
}
</style>