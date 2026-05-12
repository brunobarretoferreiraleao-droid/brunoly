<div class="bg"></div>
<div class="noise"></div>
<div class="water"></div>

<style>
.bg {
  position: fixed;
  inset: 0;
  z-index: -2;

  background:
    radial-gradient(circle at 20% 15%, rgba(127, 214, 255, 0.35), transparent 45%),
    radial-gradient(circle at 80% 25%, rgba(126, 240, 214, 0.25), transparent 50%),
    radial-gradient(circle at 50% 80%, rgba(120, 190, 255, 0.25), transparent 55%),

    linear-gradient(to bottom,
      #8bc9ee 0%,
      #4f89c5 45%,
      #1e4f86 100%
    );

  filter: saturate(0.9) contrast(1);
}

/* camada viva */
.water {
  position: fixed;
  inset: 0;
  z-index: -1;

  background:
    radial-gradient(circle at var(--mx, 50%) var(--my, 50%),
      rgba(126, 240, 214, 0.18),
      transparent 60%),

    radial-gradient(circle at 30% 70%,
      rgba(120, 190, 255, 0.15),
      transparent 60%);

  mix-blend-mode: screen;
  filter: blur(45px);
  animation: drift 14s ease-in-out infinite;
}

.noise {
  position: fixed;
  inset: 0;

  background-image: url('static/noise.avif ');

  opacity: 0.035;

  mix-blend-mode: soft-light;

  pointer-events: none;

  z-index: 999;
}

@keyframes drift {
  0% { transform: translate(0,0) scale(1); }
  50% { transform: translate(-25px, 20px) scale(1.06); }
  100% { transform: translate(0,0) scale(1); }
}
</style>