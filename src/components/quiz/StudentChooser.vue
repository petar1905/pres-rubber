<script>
export default {
  mounted() {
    const classmates = [
      "Александър Георгиев","Атанас Кацунов",
      "Ванеса Ивайлова","Ванеса Николова",
      "Виктор Петков","Георги Георгиев",
      "Георги Йорданов","Дейвид Николов",
      "Ивайло Дудеков","Иван-Игнат Димитров",
      "Иво Сирашки","Калоян Богданов",
      "Мила Атанасова","Никола Илиев",
      "Николай Гетов","Николай Нецов",
      "Силвана Василева","Цветомир Дяков",
      "Цветослав Марковски","Явор Георгиев",
      "Надя Петрова","Никола Стоилов",
      "Мария Данева","Борислава Гаврилова"
    ]
    const Button = this.$refs.Button
    const Result = this.$refs.Result
    const Classmate = this.$refs.Classmate

    Button.addEventListener("click", () => {
      Button.style.display = "none"
      Result.style.display = "flex"
      let CurrentClassmate = Math.floor(Math.random() * classmates.length)
      Classmate.innerHTML = classmates[CurrentClassmate]
      classmates.splice(CurrentClassmate, 1)
    })

    Classmate.addEventListener("click", () => {
      let CurrentClassmate = Math.floor(Math.random() * classmates.length)
      Classmate.innerHTML = classmates[CurrentClassmate]
      classmates.splice(CurrentClassmate, 1)
    })
  }
}
</script>

<template>
  <div id="Button" ref="Button">
    <h1>Избери ученик</h1>
  </div>
  <div id="Result" ref="Result">
    <p style="margin-top: 0px;">На въпроса ще отговори...</p>
    <div style="display: flex; justify-content: center;">
      <h2 ref="Classmate" id="Classmate">Иван Иванов</h2>
    </div>
  </div>
</template>

<style scoped>
  #Button {
    display: flex;
    justify-content: center;
  }

  #Result {
    display: none;
    flex-direction: column;
    justify-content: center;
  }

  h1 {
    width: 50%;
    padding: 40px;
  }

  #Classmate {
    padding: 40px;
    margin: 0px;
    width: 80%;
    margin-bottom: 57px;
  }

  h1, #Classmate {
    transition: .3s linear;
    border-radius: 20px;
  }

  h1:hover, #Classmate:hover {
    background-color: white;
    color: black;
    cursor: pointer;
  }
</style>