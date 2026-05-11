<script lang="ts">
  let x = $state(0);
  let y = $state(0);

  function move(e: MouseEvent) {
    x = e.clientX;
    y = e.clientY;
  }
</script>

<div class="cursor-glow" style="left: {x}px; top: {y}px;">

</div>

<svelte:window on:mousemove={move} />

<style>
.cursor-glow {
  position: fixed;
  width: 300px;
  height: 300px;

  transform: translate(-50%, -50%);
  pointer-events: none;

  background: radial-gradient(
    circle,
    rgba(125,220,255,0.25),
    transparent 60%
  );

  filter: blur(20px);
  transition: left 0.08s ease, top 0.08s ease;
  z-index: 9999;
}
</style>