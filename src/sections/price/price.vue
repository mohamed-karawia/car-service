<template>
  <section class="price" id="price">
    <p>We take money only for a quality work done.</p>
    <div class="price__heading">
      <h2>Price of our services</h2>
    </div>
    <div class="price__brands">
      <div
        :class="[
          brand === 1 ? 'price__brands__brand active' : 'price__brands__brand',
        ]"
        @click="brand = 1"
      >
        <img src="../../assets/img/brands-4.png" alt="" />
      </div>
      <div
        :class="[
          brand === 2 ? 'price__brands__brand active' : 'price__brands__brand',
        ]"
        @click="brand = 2"
      >
        <img src="../../assets/img/brands-1.png" alt="" />
      </div>
      <div
        :class="[
          brand === 3 ? 'price__brands__brand active' : 'price__brands__brand',
        ]"
        @click="brand = 3"
      >
        <img src="../../assets/img/brands-2.png" alt="" />
      </div>
    </div>
    <Table :brand="currentBrand" />
  </section>
</template>

<script>
import Table from "../../components/price/priceTable.vue";

export default {
  data() {
    return {
      brand: 1,
      brandOne: [
        { name: "Service", description: "Replace", price: "10" },
        { name: "Service", description: "Replace", price: "10" },
        { name: "Service", description: "Replace", price: "10" },
        { name: "Service", description: "Replace", price: "10" },
        { name: "Service", description: "Replace", price: "10" },
        { name: "Service", description: "Replace", price: "10" },
      ],
      brandTwo: [
        { name: "Service2", description: "Replace", price: "20" },
        { name: "Service2", description: "Replace", price: "20" },
        { name: "Service2", description: "Replace", price: "20" },
        { name: "Service2", description: "Replace", price: "20" },
        { name: "Service2", description: "Replace", price: "20" },
        { name: "Service2", description: "Replace", price: "20" },
      ],
      brandThree: [
        { name: "Service3", description: "Replace", price: "30" },
        { name: "Service3", description: "Replace", price: "30" },
        { name: "Service3", description: "Replace", price: "30" },
        { name: "Service3", description: "Replace", price: "30" },
        { name: "Service3", description: "Replace", price: "30" },
        { name: "Service3", description: "Replace", price: "30" },
      ],
    };
  },
  components: {
    Table,
  },
  computed: {
    currentBrand() {
      switch (this.brand) {
        case 1:
          return this.brandOne;
        case 2:
          return this.brandTwo;
        case 3:
          return this.brandThree;
        default:
          return this.brandOne;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.price {
  background-color: #ffff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  padding: 6rem 3rem;

  @media only screen and (max-width: 900px) {
    padding: 6rem 0.5rem;
  }

  p {
    @include sectionP;

    @media only screen and (max-width: 376px) {
      padding: 0 1rem;
    }

    @media only screen and (max-width: 357px) {
      padding: 0 2rem;
    }
  }

  &__heading {
    @include sectionHeading;
  }

  &__brands {
    display: flex;
    margin-top: 2rem;
    width: 25rem;

    @media only screen and (max-width: 900px) {
      width: 90%;
    }

    &__brand {
      flex: 1;
      border: 1px solid #f1f1f1;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 1rem;
      cursor: pointer;
      background-color: #f8f8f8;

      &.active {
        background-color: white;
        border-top: 3px solid $primary-color;
      }

      img {
        width: 100%;
      }
    }
  }
}
</style>