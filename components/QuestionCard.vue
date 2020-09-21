<template>
  <div class="shadow-md p-3">
    <div class="flex flex-row justify-center">
      <span>{{ question.question }}</span>
    </div>
    <div class="flex flex-col align-middle gap-1">
      <button
        v-for="answer in question.possibleAnswers"
        :key="answer.key"
        class="answer-button"
      >
        {{ answer.value }}
      </button>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    question: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      correctAnswer: this.question.correctAnswer,
      chosenAnswer: '',
    }
  },
  computed: {
    dynamicColor: {},
  },
}
</script>

<style lang="postcss">
.answer-button {
  @apply bg-blue-500 text-red-800 font-bold py-2 px-4 rounded;
}
.answer-button:hover {
  @apply bg-blue-700;
}

.answer-button:focus {
  @apply outline-none;
}
</style>
