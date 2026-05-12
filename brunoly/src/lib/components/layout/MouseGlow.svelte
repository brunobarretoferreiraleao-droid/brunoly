<script lang="ts">
  let mouseX = $state(0);
  let mouseY = $state(0);

  function move(e: MouseEvent) {
    mouseX = e.clientX;
    mouseY = e.clientY;
  }
</script>

<svelte:window on:mousemove={move} />

<div
  class="glow"
  style="left:{mouseX - 210}px; top:{mouseY - 210}px;"
></div>

<style>
.glow {
  position: fixed;
  width: 420px;
  height: 420px;

  pointer-events: none;
  z-index: 9999;

  border-radius: 50%;

  background: radial-gradient(
    circle,
    rgba(120, 220, 255, 0.14),
    transparent 60%
  );

  filter: blur(60px);
  opacity: 0.55;
}
</style>