<script lang="ts">
  let bubbles = $state<{ x: number; y: number; id: number }[]>([]);
  let id = 0;

  function click(e: MouseEvent) {
    bubbles = [
      ...bubbles,
      { x: e.clientX, y: e.clientY, id: id++ }
    ];

    setTimeout(() => {
      bubbles = bubbles.slice(1);
    }, 500);
  }
</script>

<svelte:window on:click={click} />

{#each bubbles as b (b.id)}
  <div
    class="bubble"
    style="left:{b.x}px; top:{b.y}px;"
  ></div>
{/each}

<style>
.bubble {
  position: fixed;

  width: 10px;
  height: 10px;

  border-radius: 50%;
  pointer-events: none;

  transform: translate(-50%, -50%);

  background: rgba(255,255,255,0.35);

  animation: pop 0.5s ease-out forwards;

  z-index: 5000;
}

@keyframes pop {
  0% {
    transform: translate(-50%, -50%) scale(0.8);
    opacity: 0.5;
  }

  100% {
    transform: translate(-50%, -50%) scale(2.5);
    opacity: 0;
  }
}
</style>