<template>
  <section class="about" id="about">
    <div class="about__header">About us</div>
    <div class="about__details">
      <div class="about__details__text">
        Our service center offers a comprehensive approach to the maintenance of
        the car, as a result of which you will be given an objective assessment
        of the condition of the car.<br /><br />In addition, there is no need to
        go anywhere else, since every car enthusiast will find everything he
        needs! And since every modern person really appreciates his time, with
        our help he will be able to feel all the advantages of a qualitative and
        operational approach to car repair.<br /><br />
        Our service center offers a comprehensive approach to the maintenance of
        the car, as a result of which you will be given an objective assessment
        of the condition of the car, as a result of which you will be given an
        objective assessment of the condition of the car, there is no need to go
        anywhere else, since every car enthusiast will find everything he needs!
      </div>
      <img src="../../assets/img/content-2.jpg" alt="cars" />
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.about {
  padding: 7rem;

  @media only screen and (max-width: 1038px) {
    padding: 5rem 2rem;
  }

  &__header {
    height: 4rem;
    font-size: 2.5rem;
    font-weight: 900;
    position: relative;
    margin-bottom: 1rem;

    &::after {
      content: "";
      position: absolute;
      bottom: 0;
      left: 0;
      width: 4rem;
      height: 4px;
      background-color: $primary-color;
    }
  }

  &__details {
    display: flex;
    align-items: center;

    @media only screen and (max-width: 1038px) {
      flex-direction: column;
    }

    &__text {
      flex: 1;
      font-weight: 500;
      font-size: 1.1rem;
      padding-right: 1rem;

      @media only screen and (max-width: 1038px) {
        margin-bottom: 1rem;
      }
    }

    img {
      width: 100%;
      flex: 1;
    }
  }
}
</style>