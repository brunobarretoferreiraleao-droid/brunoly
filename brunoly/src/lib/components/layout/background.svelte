<div class="bg"></div>

<style>
.bg {
  position: fixed;
  inset: 0;
  z-index: -1;

  background:
    radial-gradient(circle at 20% 20%, rgba(94,234,212,0.18), transparent 40%),
    radial-gradient(circle at 80% 30%, rgba(125,220,255,0.18), transparent 45%),
    radial-gradient(circle at 40% 80%, rgba(96,165,250,0.15), transparent 50%);

  filter: blur(60px);
  animation: drift 18s ease-in-out infinite;
}

@keyframes drift {
  0% { transform: translate(0,0) scale(1); }
  50% { transform: translate(20px,-30px) scale(1.05); }
  100% { transform: translate(0,0) scale(1); }
}
</style>