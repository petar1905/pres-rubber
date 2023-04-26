<script>
import Entry from "./components/Entry.vue"
import Menu from "./components/menu/Menu.vue"
export default {components: {Entry, Menu}}
</script>

<template>
  <Entry></Entry>
  <header>
    <Menu id="Menu"></Menu>
  </header>
  <Congrats></Congrats>
</template>

<style scoped>
@font-face {
  font-family: SF-Pro;
  src: url("src/assets/fonts/SFPRODISPLAYREGULAR.OTF");
}

@font-face {
    font-family: SF-Bold;
    src: url("src/assets/fonts/SFPRODISPLAYBOLD.OTF");
}

body * {
  font-size: 2em;
  text-align: center;
  align-items: center;
  font-family: SF-Pro;
}

</style>

<style>
body {
  background: linear-gradient(90deg, hsla(213, 77%, 14%, 1) 0%, hsla(202, 27%, 45%, 1) 100%);
  background-repeat: no-repeat;
  background-attachment: fixed;
}

header {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

#Menu {
  margin-top: 50px;
}
</style>