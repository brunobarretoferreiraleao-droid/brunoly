<div class="bg"></div>

<style>
.bg {
  position: fixed;
  inset: 0;
  z-index: -1;

  background:
    radial-gradient(
      circle at var(--mx) var(--my),
      rgba(125, 220, 255, 0.22),
      transparent 40%
    )
    radial-gradient(circle at 20% 30%, rgba(125, 220, 255, 0.22), transparent 45%),
    radial-gradient(circle at 80% 20%, rgba(94, 234, 212, 0.18), transparent 50%),    
}

@keyframes float {
  0% {
    transform: translate(0, 0) scale(1);
  }

  50% {
    transform: translate(40px, -30px) scale(1.05);
  }

  100% {
    transform: translate(0, 0) scale(1);
  }
}

/* noise overlay (ESSENCIAL pro Frutiger Aero feel) */
.bg::after {
  content: "";
  position: absolute;
  inset: 0;

  background-image: url("/noise.png");
  opacity: 0.04;

  pointer-events: none;
}
</style>