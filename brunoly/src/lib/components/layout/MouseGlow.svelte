<script lang="ts">
  import { onMount } from 'svelte';

  let mouseX = $state(0);
  let mouseY = $state(0);

  function move(e: MouseEvent) {
    mouseX = e.clientX;
    mouseY = e.clientY;
  }

  function animate() {
    document.documentElement.style.setProperty('--mx', `${mouseX}px`);
    document.documentElement.style.setProperty('--my', `${mouseY}px`);

    requestAnimationFrame(animate);
  }

  onMount(() => {
    window.addEventListener('mousemove', move);

    animate();

    return () => {
      window.removeEventListener('mousemove', move);
    };
  });
</script>

<svelte:window on:mousemove={move} />

<div
  class="glow"
  style="left: calc(var(--mx) - 210px); top: calc(var(--my) - 210px);">
</div>

<style>
.glow {
  position: fixed;

  width: 420px;
  height: 420px;

  position: fixed;  pointer-events: none;
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