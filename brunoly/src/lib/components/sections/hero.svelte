<script lang="ts">
  import { onMount } from 'svelte';
  import gsap from 'gsap';

  let title: HTMLElement;
  let subtitle: HTMLElement;
  let button: HTMLElement;

  onMount(() => {
    const tl = gsap.timeline();

    tl.from(title, {
      y: 40,
      opacity: 0,
      duration: 1,
      ease: 'power3.out'
    })
    .from(subtitle, {
      y: 20,
      opacity: 0,
      duration: 0.8,
      ease: 'power3.out'
    }, '-=0.5')
    .from(button, {
      scale: 0.9,
      opacity: 0,
      duration: 0.6,
      ease: 'power2.out'
    }, '-=0.4');
  });
</script>

<section class="hero">
  <div class="content">
    <h1 bind:this={title}>
      Transformando ideias<br />
      em experiências.
    </h1>

    <p bind:this={subtitle}>
      Code, design, música e storytelling em movimento.
    </p>

    <button bind:this={button}>
      Explore meu universo digital.
    </button>
  </div>
</section>

<style>
.hero {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

h1 {
  font-size: clamp(3rem, 7vw, 6rem);
  line-height: 1;
}

p {
  font-family: var(--font-ui);
  margin-top: 1rem;
  opacity: 0.7;
}

button {
  margin-top: 2rem;
  padding: 1rem 2rem;

  border-radius: 999px;
  border: none;

  background: rgba(255,255,255,0.08);
  backdrop-filter: blur(20px);

  cursor: pointer;
}
</style>