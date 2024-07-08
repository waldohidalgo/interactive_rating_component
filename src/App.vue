<script>
import Question from "./components/Question.vue";
import Answer from "./components/Answer.vue";
import Footer from "./components/Footer.vue";
export default {
  data() {
    return {
      rating: 0,
      isRated: false,
    };
  },
  components: {
    Question,
    Answer,
    Footer,
  },

  methods: {
    setRating(rating) {
      this.rating = rating;
    },

    submitRating() {
      if ([1, 2, 3, 4, 5].includes(this.rating)) {
        this.isRated = true;
      }
    },
  },
};
</script>

<template>
  <main class="py-[153px] bg-veryDarkBlue sm:pt-[194px]">
    <div
      class="bg-darkBlue w-[87%] rounded-[13px] mx-auto max-w-[416px] sm:rounded-[31px]"
    >
      <Answer v-if="isRated" :rating="rating" />
      <Question
        v-else
        @setRating="setRating"
        :rating="rating"
        @submitRating="submitRating"
      />
    </div>
  </main>
  <Footer />
</template>
