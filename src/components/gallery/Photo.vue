<script>
export default {
  props: ['Content', 'Alt', 'Width'],
  mounted() {
  const Photo = this.$refs.Photo
  const Alt = this.$refs.Alt
  Photo.style.backgroundImage = `url(${this.Content})`
  let isZoomed = false
  if (this.Width !== undefined) Photo.style.width = this.Width
  
  Photo.addEventListener("click", () => {
    switch (isZoomed) {
    case true:
      Photo.style.zIndex = "0"
      Photo.style.animation = "ZoomOut 1s cubic-bezier(0.215, 0.610, 0.355, 1)"
      Photo.style.animationDirection = "normal"
      Photo.style.animationFillMode = "forwards"
      Alt.style.opacity = "0"
      setTimeout(() => {Alt.style.display = "none"}, 1000)
      isZoomed = false
      setTimeout(() => {Photo.style.animation = "none"}, 1100)
      break
    
    case false:
      Alt.style.display = "block"
      Photo.style.zIndex = "1"
      Photo.style.animation = "ZoomIn 1s cubic-bezier(0.215, 0.610, 0.355, 1)"
      Photo.style.animationDirection = "normal"
      Photo.style.animationFillMode = "forwards"
      setTimeout(() => {Alt.style.opacity = "1"}, 100)
      isZoomed = true
      break
    }
  })
  }
}
</script>

<template>
<div id="Wrapper">
  <div id="Photo" ref="Photo"></div>
</div>
<p id="Alt" ref="Alt">{{ Alt }}</p>
</template>

<style scoped>
#Wrapper {
  width: 400px;
  height: 300px;
}

#Photo {
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  width: 400px;
  height: 300px;
  border-radius: 20px;
  transition: 1s;
}

#Alt {
  display: none;
  position: fixed;
  width: 100vw;
  height: 10vh;
  left: -3%;
  bottom: 0%;
  margin: 0;
  text-align: center;
  background-color: rgba(0, 0, 0, .8);
  backdrop-filter: blur(5px);
  z-index: 0;
  padding: 10px 30px;
  transition: .7s linear;
  opacity: 0;
  font-size: smaller;
}
</style>

<style>
#Photo:hover {cursor: pointer;}

@keyframes ZoomIn {
  0% {position: relative; left: 0%; top: 0%; opacity: 1}
  50% {position: relative; left: -40%; top: -40%; opacity: 0}
  51% {position: fixed; left: 0%; top: 0%; opacity: 0;}
  100% {position: fixed; left: 40%; top: 29%; opacity: 1; transform: scale(2.6); z-index: 5}
}

@keyframes ZoomOut {
  0% {position: fixed; left: 40%; top: 29%; opacity: 1; ; transform: scale(2.6)}
  50% {position: fixed; left: 0%; top: 0%; opacity: 0;}
  51% {position: relative; left: -40%; top: -40%; opacity: 0}
  100% {position: relative; left: 0%; top: 0%; opacity: 1; z-index: 0}
}
/* position change should be animatable :p*/
</style>