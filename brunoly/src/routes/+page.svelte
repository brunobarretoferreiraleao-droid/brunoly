<script lang="ts">
  import Hero from '$lib/components/sections/hero.svelte';
  import About from '$lib/components/sections/about.svelte';
</script>

<main class="page">
  <Hero />

  <section class="spacer" >
    
  </section>

  <About />
</main>

<style>
.page {
  display: flex;
  flex-direction: column;
}

.spacer {
  height: 25vh;
}
</style>
