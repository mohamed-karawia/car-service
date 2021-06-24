<template>
  <section class="contact" id="contact">
    <div class="contact--items">
      <div class="contact--item">
        <svg class="contact--icon">
          <use xlink:href="../../assets/sprite.svg#icon-map-o"></use>
        </svg>
        <h2 class="contact--heading">Our Adress</h2>
        <p class="contact--details">550 Mill Pond Ave. Melburn, MA 02474</p>
      </div>

      <div class="contact--item">
        <svg class="contact--icon">
          <use xlink:href="../../assets/sprite.svg#icon-mobile"></use>
        </svg>
        <h2 class="contact--heading">Our Phones</h2>
        <p class="contact--details">+1(970) 744-80-26</p>
      </div>

      <div class="contact--item">
        <svg class="contact--icon">
          <use xlink:href="../../assets/sprite.svg#icon-envelope-open"></use>
        </svg>
        <h2 class="contact--heading">E-mail</h2>
        <p class="contact--details">info@domaine.com</p>
      </div>
    </div>

    <div class="map--container">
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d22772.118555350327!2d26.110488!3d44.484117!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xc9ac8c7529a47d43!2sNeortic%20Motors!5e0!3m2!1sen!2sro!4v1624437489307!5m2!1sen!2sro"
        width="100%"
        height="450"
        style="border: 0"
        allowfullscreen=""
        loading="lazy"
      ></iframe>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.contact {
  width: 100%;
  padding: 5rem 3rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: column;

      @media only screen and (max-width: 785px) {
    padding: 5rem 1rem;
  }

  &--items {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    margin-bottom: 3rem;

      @media only screen and (max-width: 785px) {
    flex-direction: column;
  }
  }

  &--item {
    display: flex;
    flex-direction: column;
    align-items: center;
    flex: 1;

    @media only screen and (max-width: 785px) {
      margin-bottom: 1rem;
    }

    & > * {
      margin-bottom: 1rem;
    }
  }

  &--icon {
    width: 5rem;
    height: 5rem;
    fill: $primary-color;
    transition: all .2s;
    cursor: pointer;

    &:hover{
      scale: 1.1;
    }
  }

  &--heading {
    text-transform: capitalize;
    color: #7e7e7e;
  }

  &--details {
    color: #7e7e7e;
  }

  .map--container{
      width: 100%;
  }
}
</style>