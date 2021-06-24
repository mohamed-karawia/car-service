<template>
  <div class="review">
    <img :src="review.img" alt="review" />
    <h2>{{ review.heading }}</h2>
    <p>{{ review.text }}</p>
    <h3>{{ review.user }}</h3>
  </div>
</template>

<script>
export default {
  props: {
    review: Object,
  },
};
</script>

<style lang="scss" scoped>
.review {
  background-color: white;
  width: 40rem;
  margin: 2rem 0;
  position: relative;
  padding: 2rem 3rem;
  display: flex;
  flex-direction: column;

  box-shadow: 10px 10px 10px -5px rgba(0, 0, 0, 0.281);
  -webkit-box-shadow: 10px 10px 10px -5px rgba(0, 0, 0, 0.281);
  -moz-box-shadow: 10px 10px 10px -5px rgba(0, 0, 0, 0.281);

  @media only screen and (max-width: 720px) {
    width: 100%;
  }

  & > * {
    margin-bottom: 2rem;
  }

  img {
    position: absolute;
    width: 10rem;
    left: -20%;
    top: 3%;

    border: 5px solid white;
    border-radius: 50%;

    @media only screen and (max-width: 900px) {
        position: static;
        align-self: center;
    }
  }

  h2 {
    text-transform: capitalize;
    font-weight: 900;
  }

  p {
    font-size: 1.1rem;
    line-height: 1.3rem;
    font-weight: 300;
  }
}
</style>