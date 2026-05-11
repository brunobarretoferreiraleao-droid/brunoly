<script lang="ts">
  import Background from '$lib/components/layout/Background.svelte';
  import MouseGlow from '$lib/components/layout/MouseGlow.svelte';
  import ClickRipple from '$lib/components/layout/ClickRipple.svelte';
  import ClickBubbles from '$lib/components/layout/ClickBubbles.svelte';
  import Navbar from '$lib/components/layout/Navbar.svelte';

    let { children } = $props();
</script>

<Background />
<MouseGlow />
<ClickRipple />
<ClickBubbles />

<Navbar />

{@render children?.()}