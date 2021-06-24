<template>
  <section class="reviews" id="reviews">
    <p>What customers are saying</p>
    <div class="reviews__heading">
      <h2>Reviews about us</h2>
    </div>
    <Review v-for="(review, index) in reviews" :key="index" :review="review" />
  </section>
</template>

<script>
import Review from "../../components/Reviews/Review.vue";
import img1 from "../../assets/img/reviews-4.png";
import img2 from "../../assets/img/reviews-5.png";
import img3 from "../../assets/img/reviews-6.png";

export default {
  data() {
    return {
      reviews: [
        {
          img: img1,
          heading:
            "I paid exactly the amount that was called in the beginning ...",
          text: "In the spring I decided to update the car - freshen up the color, remove the scratches on the sides. After inspection and diagnosis, the car was named the normal price, I immediately agreed! the painting took only three days. When I saw the car, I liked everything, paid exactly the amount that was called in the beginning. Pokras24, thanks for the quality work !!! ",
          user: "Emil, 43 years old, Audi TT",
        },
        {
          img: img2,
          heading:
            "there will be an opportunity - I will turn to Pokras24 again!",
          text: "thank you guys for the excellent work! Has got in failure, has broken the Audi, awful history! I decided to pay for repairs in Pokras24, I was very worried, I was afraid that they would paint badly, at random, Unsuccessfully pick up the color. the result was very pleased, they did everything qualitatively and quickly. there will be an event - Turn to Pokras24 yet! thank you!",
          user: "Daniel, 38 years old, Hyundai Accent ",
        },
        {
          img: img3,
          heading: "Within 4 days I took the car ...",
          text: "For a long time I was looking for a service to repair a car, most companies offer their services at inflated prices, and even the quality of work leaves much to be desired. the prices are adequate and the quality of work is at a high level. What pleased in Pokras24 - everything was done quickly, after 4 days I took the car. Appealed on the advice of a friend and do not regret!",
          user: "Mersedes, 35y.o., Mazda 6",
        },
      ],
    };
  },
  components: {
    Review,
  },
};
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.reviews {
  background-color: $gray;
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
  }

  &__heading {
    @include sectionHeading;
  }
}
</style>