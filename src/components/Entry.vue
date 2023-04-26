<script>
export default {
  mounted() {
    const TitleScreen = this.$refs.TitleScreen
    const Start = this.$refs.Start

    Start.addEventListener("click", () => {
      TitleScreen.style.transition = "1s"
      TitleScreen.style.marginTop = "-100%"
      setTimeout(() => {
        TitleScreen.style.display = "none"
      }, 1000)
    })
  }
}
</script>

<template>
<div ref="TitleScreen" >
  <p>Урок по Химия и Опазване на околната среда</p>
  <h1 id="Start" ref="Start">Каучук</h1>
  <p>Изготвен от <i>Петър Владов</i> и <i>Петър Славов</i></p>
</div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  position: fixed;
  width: 100vw;
  height: 100vh;
  backdrop-filter: blur(5px);
  background-color: rgba(0, 0, 0, 0.8);
  z-index: 2;
}

div * {
  justify-content: center;
  color: white;
}

h1, i {
  font-family: SF-Bold;
  padding: 20px;
  border-radius: 20px;
}

h1:hover, i {
  background-color: white;
  color: black;
}

h1, p {transition: .3s linear}
h1:hover {cursor: pointer;}
#Start {padding: 100px;}

h1 {font-size: 4em}
p {font-size: 2em}
</style>