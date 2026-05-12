<script lang="ts">
  import Background from '$lib/components/layout/Background.svelte';
  import MouseGlow from '$lib/components/layout/MouseGlow.svelte';
  import ClickRipple from '$lib/components/layout/ClickRipple.svelte';
  import ClickBubbles from '$lib/components/layout/ClickBubbles.svelte';
  import Navbar from '$lib/components/layout/Navbar.svelte';

  import { onMount } from 'svelte';
  import Lenis from 'lenis';

  onMount(() => {
    const lenis = new Lenis({
      duration: 1.2,
      smoothWheel: true,
    });

    function raf(time: number) {
      lenis.raf(time);
      requestAnimationFrame(raf);
    }
    requestAnimationFrame(raf);
  });

  let { children } = $props();
</script>

<Background />
<MouseGlow />
<ClickRipple />
<ClickBubbles />

<Navbar />

<!-- 🌐 GRID GLOBAL -->
<div class="page-grid">
  {@render children?.()}
</div>

<style>
.page-grid {
  display: grid;
  grid-template-columns: 1fr min(1100px, 92vw) 1fr;
}

.page-grid > :global(*) {
  grid-column: 2;
}
</style>