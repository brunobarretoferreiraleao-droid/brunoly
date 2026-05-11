<script lang="ts">
  let bubbles = $state<{ x: number; y: number; id: number }[]>([]);
  let id = 0;

  function click(e: MouseEvent) {
    bubbles = [...bubbles, { x: e.clientX, y: e.clientY, id: id++ }];
    setTimeout(() => {
      bubbles = bubbles.slice(1);
    }, 800);
  }
</script>

<svelte:window on:click={click} />

{#each bubbles as b (b.id)}
  <div class="bubble" style="left:{b.x}px; top:{b.y}px;">
  </div>
{/each}

<style>
.bubble {
  position: fixed;
  width: 20px;
  height: 20px;

  transform: translate(-50%, -50%);
  border-radius: 50%;

  background: rgba(125,220,255,0.4);

  animation: pop 0.8s ease-out forwards;
  pointer-events: none;
}

@keyframes pop {
  0% {
    transform: translate(-50%, -50%) scale(0.5);
    opacity: 0.8;
  }
  100% {
    transform: translate(-50%, -50%) scale(8);
    opacity: 0;
  }
}
</style>