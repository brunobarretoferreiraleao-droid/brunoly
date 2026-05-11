<script lang="ts">
  let x = 0;
  let y = 0;

  let dx = $state(0);
  let dy = $state(0);

  function move(e: MouseEvent) {
    x = e.clientX;
    y = e.clientY;
  }

  function animate() {
    dx += (x - dx) * 0.08;
    dy += (y - dy) * 0.08;

    requestAnimationFrame(animate);
  }

  animate();
</script>

<svelte:window on:mousemove={move} />

<div
  class="glow"
  style="transform: translate({dx}px, {dy}px)"
>

</div>

<style>
.glow {
  position: fixed;
  top: 0;
  left: 0;

  width: 420px;
  height: 420px;

  transform: translate(-50%, -50%);
  pointer-events: none;

  background: radial-gradient(
    circle,
    rgba(120, 220, 255, 0.14),
    transparent 60%
  );

  filter: blur(30px);
  opacity: 0.9;

  mix-blend-mode: screen;

  transition: opacity 0.3s ease;
  z-index: 9999;
}
</style>