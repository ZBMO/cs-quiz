<template>
  <div class="container">
    <question-card
      v-for="question in questionList"
      :key="question.question"
      :question="question"
    ></question-card>
  </div>
</template>

<script>
import QuestionCard from '~/components/QuestionCard'
import QuestionFile from '~/store/algorithmCache.json'

export default {
  components: {
    QuestionCard,
  },
  data() {
    return {
      questionList: QuestionFile.questions,
    }
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
