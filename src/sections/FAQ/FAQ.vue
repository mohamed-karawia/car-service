<template>
  <section class="faq">
    <p>
      Aliquam a augue suscipit, bibendum luctus neque vestibulum laoreet rhoncus
      ipsum, bibendum tempor vulputate varius
    </p>
    <div class="faq__heading">
      <h2>FAQ</h2>
    </div>
    <div class="faq__accordion--container">
      <faq-accordion v-for="(question, index) in questions" :key="index" :question="question"/>
    </div>
  </section>
</template>

<script>
import faqAccordion from "../../components/faqAccordion/faqAccordion.vue";

export default {
  components: {
    faqAccordion,
  },
  data() {
    return {
      questions: [
        {
          question: "Expensive Oil Changes Are Here to Stay",
          answer:
            "Oil changes may be more expensive with the required 0W-20 weight oil compared to conventional oil, but only having to service the car once or twice a year keeps annual costs to nearly a wash. ",
        },
        {
          question: "What's Included in a Tuneup?",
          answer:
            "Actually, there is no such thing as a tuneup in the traditional sense of replacing parts to bring the ignition and fuel systems up to specs for maximum performance and efficiency... ",
        },
        {
          question: "Change Your Oil Every 3,000 Miles?",
          answer:
            "No, you don't, according to every auto manufacturer we've talked to. the main advocates of the 3,000-mile oil change schedule are those who would profit by it...",
        },
        {
          question: "Expensive Oil Changes Are Here to Stay",
          answer:
            "Oil changes may be more expensive with the required 0W-20 weight oil compared to conventional oil, but only having to service the car once or twice a year keeps annual costs to nearly a wash. ",
        },
        {
          question: "What's Included in a Tuneup?",
          answer:
            "Actually, there is no such thing as a tuneup in the traditional sense of replacing parts to bring the ignition and fuel systems up to specs for maximum performance and efficiency... ",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.faq {
  background-color: #ffff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  padding: 6rem 3rem;

      @media only screen and (max-width: 900px){
        padding: 6rem .5rem;
    }

  p {
    @include sectionP;
  }

  &__heading {
    @include sectionHeading;
  }

  &__accordion--container {
    width: 70%;
    margin-top: 3rem;

    @media only screen and (max-width: 900px){
        width: 100%;
    }
  }
}
</style>