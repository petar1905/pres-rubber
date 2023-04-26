<template>
<div>
  <slot></slot>
</div>
</template>

<style scoped>
div {
  color: white;
  display: flex;
  flex-direction: column;
  width: 100vw;
  height: 100vh;
  overflow-y: scroll;
  overflow-x: hidden;
  scroll-behavior: smooth;
}

/* width */
::-webkit-scrollbar {
  width: 20px;
}

/* Track */
::-webkit-scrollbar-track {
  background-color: rgba(0,0,0, 0.5);
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: white;
}
</style>