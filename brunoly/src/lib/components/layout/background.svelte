<div class="bg"></div>

<div class="water"></div>

<style>
.bg {
  position: fixed;
  inset: 0;
  z-index: -2;

  /* CÉU + LUZ ATMOSFÉRICA */
  background:
    radial-gradient(circle at 20% 10%, rgba(180, 255, 240, 0.35), transparent 40%),
    radial-gradient(circle at 80% 20%, rgba(120, 200, 255, 0.35), transparent 45%),
    radial-gradient(circle at 50% 80%, rgba(140, 255, 200, 0.2), transparent 55%),

    linear-gradient(to bottom,
      #a6f0ff 0%,
      #6fb6ff 40%,
      #2b6cb0 100%
    );

  filter: saturate(1.2) contrast(1.05);
}

/* CAMADA DE ÁGUA */
.water {
  position: fixed;
  inset: 0;
  z-index: -1;

  background:
    radial-gradient(circle at var(--mx, 50%) var(--my, 50%),
      rgba(255,255,255,0.18),
      transparent 60%);

  mix-blend-mode: screen;

  filter: blur(40px);

  animation: flow 12s ease-in-out infinite;
}

/* movimento orgânico tipo superfície de água */
@keyframes flow {
  0% {
    transform: translate(0,0) scale(1);
  }

  50% {
    transform: translate(-30px, 20px) scale(1.08);
  }

  100% {
    transform: translate(0,0) scale(1);
  }
}
</style>