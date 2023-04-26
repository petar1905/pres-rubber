<script>
import Photo from "../gallery/Photo.vue"
import StudentChooser from "./StudentChooser.vue"
import Question from "./Question.vue"
import Option from "../menu/Option.vue"
export default {
  components: {Photo, StudentChooser, Question, Option},
  data() {
    return {correctAnswers: 0}
  }
}
</script>

<template>
  <div style="display: flex;">
    <div id="TopBar">
      <p>Оценка: {{ (correctAnswers/8)*100 }}%</p>
    </div>
  </div>
  <div id="MiddleArea">
    <StudentChooser></StudentChooser>
  </div>

  <Question Question="Какъв каучук се използва за изопреновите костюми?"
  a="Хлоропренов" b="Полиизопренов" c="Естествен" d="Нитрилов" Correct="a"></Question>

  <Question Question="С каква цел се осъществява процеса вулканизация?"
  a="Изгаряне на каучука" b="Разтягане на каучука" 
  c="Подобряване на каучука" d="Отделяне на каучука от латекса" Correct="c"></Question>

  <Question Question="Кой е главния недостатък на естествения каучук?"
  a="Трудно достъпен" b="Ниска устойчивост към екстремни температури" 
  c="Ниска продължителност на живота" d="Замърсява природата" Correct="b"></Question>

  <Question Question="Каква е основната разлика между зимните и летните гуми?"
  a="Формата на гумите" b="Присъствието на различни вещества в двата вида" 
  c="Начина на производство" d="Количеството каучук, използвано в гумата" Correct="d"></Question>

  <Question Question="Кое се изгражда от рециклирани гуми?"
  a="Плочки" b="Нови гуми" c="Форми" d="Ръкавици" Correct="a"></Question>

  <Question Question="Кой е главния недостатък на синтетичния каучук?"
  a="Трудно достъпен" b="Ниска надеждност" 
  c="Ниска устойчивост към екстремни температури" d="Замърсява природата" Correct="b"></Question>

  <Question Question="Кое от следните изделия е създадено от нитрилов каучук?"
  a="Маркуч" b="Медицински ръкавици" c="Форми" d="Гуми" Correct="b"></Question>

  <Question Question="Какви промени настъпват в каучука при вулканизация?"
  a="Хлоропренов" b="Окислително-редукционни процеси" c="Удвояване на количеството" 
  d="Образуват се по-силни връзки между ММ-те на каучука" Correct="d"></Question>

  <div style="display: flex; justify-content: center;">
    <Option Title="Поздрав-<br>ления!" Subtitle="Вие успяхте!" Thumbnail="photos/quiz.webp"
    Background="linear-gradient(0deg, rgba(34,193,195,1) 0%, rgba(73,142,79,1) 100%)">
    <h1>Благодарим за вниманието!</h1>  
    <div style="display: flex; justify-content: center; margin-top: -40px">
        <video src="/videos/CongratsVideo.mp4" controls id="Congrats"></video>
      </div>
    </Option>
  </div>
</template>

<style scoped>
  #TopBar {
    width: 100%;
    height: 90%;
    margin-top: 0px;
    background-color: rgb(69, 0, 133);
    text-align: center;
  }

  #MiddleArea {
    width: 100%;
    height: 50%;
  }

  #Congrats {
    width: 40%;
    height: auto;
    border-radius: 20px;
  }
</style>