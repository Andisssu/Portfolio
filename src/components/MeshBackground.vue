<!-- filepath: c:\Users\netod\OneDrive\Documentos\GitHub\Portfolio\src\components\MeshBackground.vue -->
<template>
  <div class="absolute inset-0 -z-10 h-full w-full items-center px-5 py-24" id="background">
    <canvas id="meshCanvas"></canvas>
  </div>
</template>

<script>
export default {
  mounted() {
    const canvas = document.getElementById('meshCanvas');
    const ctx = canvas.getContext('2d');

    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    let stars = [];
    const starCount = 120;

    for (let i = 0; i < starCount; i++) {
      stars.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height,
        radius: Math.random() * 1.5 + 0.5,
        alpha: Math.random(),
        delta: (Math.random() * 0.02 + 0.005) * (Math.random() < 0.5 ? -1 : 1),
      });
    }

    function draw() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      for (let star of stars) {
        ctx.beginPath();
        ctx.arc(star.x, star.y, star.radius, 0, Math.PI * 2);
        ctx.fillStyle = `rgba(255, 255, 255, ${star.alpha})`;
        ctx.shadowBlur = 10;
        ctx.shadowColor = '#bb86fc';
        ctx.fill();

        star.alpha += star.delta;
        if (star.alpha <= 0 || star.alpha >= 1) star.delta *= -1;
      }

      requestAnimationFrame(draw);
    }

    draw();

    window.addEventListener('resize', () => {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    });
  },
};
</script>

<style scoped>
#background {
  position: fixed;
  top: 0;
  left: 0;
  z-index: -1;
  width: 100vw;
  height: 100vh;
  background: radial-gradient(125% 125% at 50% 10%, #00000000 40%, #63e 100%);
}

#meshCanvas {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>