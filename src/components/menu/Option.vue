<script>
import Window from "./Window.vue"
export default {
  components: {Window},
  props: ['Title', 'Subtitle', 'Thumbnail', 'Background'],
  mounted() {
  const Button = this.$refs.Button 
  const Photo = this.$refs.Photo 
  const TitleDisplay = this.$refs.TitleDisplay 
  const SubtitleDisplay = this.$refs.SubtitleDisplay 
  const OutsideText = this.$refs.OutsideText 
  const Window = this.$refs.Window 
  const CloseButton = this.$refs.CloseButton 
  

  TitleDisplay.innerHTML = this.Title
  OutsideText.innerHTML = this.Title
  SubtitleDisplay.innerHTML = this.Subtitle
  Photo.style.backgroundImage = `url(${this.Thumbnail})`
  Button.style.background = this.Background
  Window.style.background = this.Background

  let isUp = false
  Button.addEventListener("click", () => {
    if (isUp) {
      Window.style.display = "block"
      setTimeout(() => {
        Window.style.transform = "scale(1)"
      }, 100)
      
    }
    else {
      Photo.style.marginTop = "-600px"
      OutsideText.style.transform = "translateY(-160%)"
      OutsideText.style.opacity = "0"
      isUp = true
    }
  })

  CloseButton.addEventListener("click", () => {
    Window.style.transform = "scale(0)"
  })
  }
}
</script>

<template>
<div ref="Window" id="Window">
  <Window>
  <h3 ref="CloseButton">X</h3>
  <slot></slot>
  </Window>
</div>

<div style="display: flex; flex-direction: column; height: 850px">
  <div id="Button" ref="Button">
    <div id="Photo" ref="Photo"></div> 
    <div id="Text">
      <h1 ref="TitleDisplay">{{ Title }}</h1>
      <p><i ref="SubtitleDisplay">{{ Subtitle }}</i></p>
    </div>
  </div>
  <h1 ref="OutsideText" id="OutsideText">{{Title}}</h1>
</div>
</template>

<style scoped>
#Button, #Photo, #Text {
  width: 440px;
  height: 600px;
}

#Button:hover, #Photo:hover {
  cursor:pointer;
}

#Button {
  border-radius: 20px;
  overflow:hidden;
  display: block;
  transition: 1s;
  z-index: 0;
}

h1, p {color: white;}

h1 {
  font-size: 1em;
  font-family: SF-Bold;
}

p {font-size: 0.6em;}

#Photo {
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  transition: 1s;
  z-index: 1;
  margin-top: 0%
}

#OutsideText {
  margin-top: 0px;
  transition: 1s;
  z-index: -1;
}

#Window {
  display: none;
  background-color: red;
  position: fixed;
  width: 100vw;
  height: 100vh;
  top: 0%;
  left: 0%;
  opacity: 1;
  transition: .5s linear;
  transform: scale(0);
  z-index: 5;
}

#Window h3 {
  position: absolute;
  top: -50px;
  right: 60px;
  transition: 0.3s linear;
  border-radius: 20px;
  padding: 20px 40px;
}

#Window h3:hover {
  color: black;
  background-color: white;
  cursor: pointer;
}

</style>