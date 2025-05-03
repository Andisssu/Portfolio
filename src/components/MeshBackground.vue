<!-- src/components/MeshBackground.vue -->
<template>
  <!-- <div class="mesh-background"></div> -->
  <div class="absolute inset-0 -z-10 h-full w-full items-center px-5 py-24" id="background"></div>
</template>

<style scoped>

#background{
  position: fixed;
  top: 0;
  left: 0;
  z-index: -1;
  width: 100vw;
  height: 100vh;
  background:radial-gradient(125% 125% at 50% 10%, #000000 40%,#63e 100%)
}


/*  .mesh-background {
    position: fixed;
    top: 0;
    left: 0;
    z-index: -1;
    width: 100vw;
    height: 100vh;
    background: radial-gradient(circle at 30% 30%, hsl(270, 70%, 20%) 0%, transparent 60%),
                radial-gradient(circle at 70% 40%, hsl(300, 60%, 25%) 0%, transparent 60%),
                radial-gradient(circle at 40% 80%, hsl(240, 60%, 15%) 0%, transparent 60%);
    background-blend-mode: screen;
    animation: animateGradient 10s ease-in-out infinite alternate;
    filter: blur(50px);
  }

  .mesh-background::after {
    content: "";
    position: absolute;
    inset: 0;
    background: radial-gradient(circle at center, transparent 60%, #0e0b1f 100%);
    pointer-events: none;
  }
  
  @keyframes animateGradient {
    0% {
      background-position:
        30% 30%,
        70% 40%,
        40% 80%;
    }
    100% {
      background-position:
        40% 40%,
        60% 30%,
        50% 90%;
    }
  }*/
</style>