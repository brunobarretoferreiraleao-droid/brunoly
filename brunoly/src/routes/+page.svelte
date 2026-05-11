<script lang="ts">
  import Hero from '$lib/components/sections/Hero.svelte';
  import About from '$lib/components/sections/About.svelte';
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