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
  style="transform: translate({mouseX}px, {mouseY}px)"
> </div>

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