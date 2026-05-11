<script lang="ts">
  let ripples = $state<{ x: number; y: number; id: number }[]>([]);
  let id = 0;

  function addRipple(e: MouseEvent) {
    ripples = [...ripples, { x: e.clientX, y: e.clientY, id: id++ }];

    setTimeout(() => {
      ripples = ripples.slice(1);
    }, 900);
  }
</script>

<svelte:window on:click={addRipple} />

{#each ripples as r (r.id)}
  <span class="ripple" style="left:{r.x}px; top:{r.y}px;">
  </span>
{/each}

<style>
.ripple {
  position: fixed;
  width: 20px;
  height: 20px;

  border-radius: 50%;
  transform: translate(-50%, -50%);

  background: radial-gradient(
    circle, 
    rgba(125, 220, 255, 0.25),
    transparent 70%
  );
  opacity: 0.8;

  pointer-events: none;

  animation: ripple 0.9s ease-out forwards;
}

@keyframes ripple {
  0% {
    transform: translate(-50%, -50%) scale(0.5);
    opacity: 0.8;
  }

  100% {
    transform: translate(-50%, -50%) scale(12);
    opacity: 0;
  }
}
</style>