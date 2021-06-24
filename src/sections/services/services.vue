<template>
  <section class="services" id="services">
    <p>We provide best service in the Melburn</p>
    <div class="services__heading">
      <h2>Our service</h2>
    </div>
    <services-grid />
  </section>
</template>

<script>
import servicesGrid from '../../components/Services/servicesGrid.vue'
export default {
    components:{
        servicesGrid
    }
}
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.services {
  margin-top: 6rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-bottom: 4rem;

  @media only screen and (max-width: 720px) {
    margin-top: 24rem;
  }

  p {
    @include sectionP;
  }

  &__heading {
    @include sectionHeading
  }
}
</style>