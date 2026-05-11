<script lang="ts">
  import Hero from '$lib/components/sections/hero.svelte';
  import About from '$lib/components/sections/about.svelte';
</script>

<section class="page">
  <Hero />

  <div class="spacer"></div>

  <About />
</section>

<style>
.page {
  display: flex;
  flex-direction: column;
}

.spacer {
  height: 20vh;
}
</style>