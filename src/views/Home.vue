<template>
  <div class="home">
    <Header />
    <Services />
    <Social />
    <About />
    <Reviews />
    <Price />
    <Certificate />
    <FAQ />
    <Brands />
    <Contact />
  </div>
</template>

<script>
import Header from '../sections/header/Header.vue';
import Social from '../sections/social/social.vue';
import Services from '../sections/services/services.vue';
import About from '../sections/about/about.vue';
import Reviews from '../sections/reviews/reviews.vue';
import Price from '../sections/price/price.vue';
import Certificate from '../sections/certificate/certificate.vue';
import FAQ from '../sections/FAQ/FAQ.vue';
import Brands from '../sections/brands/brands.vue';
import Contact from '../sections/contact/contact.vue';

export default {
    components:{
        Header,
        Services,
        Social,
        About,
        Reviews,
        Price,
        Certificate,
        FAQ,
        Brands,
        Contact,
    }
};
</script>

<style lang="scss" scoped>
.home{
  position: relative;
  display: flex;
  flex-direction: column;
}
</style>