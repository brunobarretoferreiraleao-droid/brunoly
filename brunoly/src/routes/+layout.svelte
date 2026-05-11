<script lang="ts">
  import Background from '$lib/components/layout/background.svelte';
  import MouseGlow from '$lib/components/layout/MouseGlow.svelte';
  import ClickBubbles from '$lib/components/layout/ClickBubbles.svelte';
  import Navbar from '$lib/components/layout/navbar.svelte';

  let { children } = $props();
</script>

<Background />
<MouseGlow />
<ClickBubbles />

<Navbar />

{@render children?.()}