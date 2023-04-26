  <script>
  export default {
    props: ["Question", "Correct", "a", "b", "c", "d"],
    data() {
      return {
        isAnswered: false
      }
    },
    methods: {
      answer(event) {
        const QuestionArea = this.$refs.QuestionArea
        
        if (event && !this.isAnswered) {
          const SelectedAnswer = event.target.id
          const IsCorrect = (SelectedAnswer == this.Correct)
          const Target = event.target
          if (IsCorrect) {
            Target.style.backgroundColor = "green"
            Target.innerHTML = "ВЯРНО"
            this.$parent.correctAnswers++
          }
          else {
            Target.style.backgroundColor = "red"
            Target.innerHTML = "ГРЕШНО"
          }
          this.isAnswered = true
          setTimeout(() => {
            QuestionArea.style.display = "none"
          }, 3000)
        }
      },
    }
  }
</script>

<template>
  <div id="QuestionArea" ref="QuestionArea">
    <p class="Question">{{ this.Question}}</p>
    <div class="AnswerRow">
      <p v-on:click="answer" id="a">{{ this.a }}</p>
      <p v-on:click="answer" id="b"> {{ this.b }}</p>
    </div>
    <div class="AnswerRow">
      <p v-on:click="answer" id="c">{{ this.c }}</p>
      <p v-on:click="answer" id="d">{{ this.d }}</p>
    </div>
  </div>
</template>

<style scoped>
  #QuestionArea {
    display: flex;
    flex-direction: column;
    width: 100%;
    padding-top: 6px;
    margin-bottom: 400px;
  }
  .AnswerRow {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
  }

  .AnswerRow p {
    transition: .2s linear;
    width: 100%;
    height: 100%;
    cursor: pointer;    
    vertical-align: middle;
    margin: auto;
    background-color: blueviolet;
    border: 3px solid;
    font-size: 1em;
  }

  .AnswerRow p:hover {
    background-color: white;
    color: black;
    border-color: white;
  }

  .Question {
    background: rgb(79, 41, 95);
    padding: 40px;
    margin: 0;
    border: 3px solid;
    border-bottom: none;
  }
</style>