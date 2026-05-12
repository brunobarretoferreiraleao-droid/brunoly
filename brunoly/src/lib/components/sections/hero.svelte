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
    <div class="visual-core">
      <div class="orb"></div>
      <div class="ring ring-1"></div>
      <div class="ring ring-2"></div>
    </div>

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
  position: relative;
  overflow: hidden;
}

h1 {
  font-size: clamp(3rem, 7vw, 6rem);

  line-height: 0.95;

  letter-spacing: -0.05em;

  background:
    linear-gradient(
      to bottom,
      #ffffff,
      #d9f4ff 35%,
      #7fd6ff 90%
    );

    background-clip: text;
    -webkit-background-clip: text;

    color: transparent;

    text-shadow:
      0 0 25px rgba(125,220,255,0.12);
    
    position: relative;

    z-index: 3;
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

.visual-core {
  position: absolute;
  inset: 0;

  display: flex;
  align-items: center;
  justify-content: center;

  pointer-events: none;
}

.orb {
  position: absolute;

  width: 440px;
  height: 440px;

  border-radius: 50%;

  background:
    radial-gradient(circle at 30% 30%,
      rgba(255,255,255,0.95),
      rgba(125,220,255,0.45) 25%,
      rgba(126,240,214,0.18) 50%,
      transparent 72%
    );

  filter: blur(10px);

  opacity: 0.95;

  box-shadow:
    0 0 120px rgba(125,220,255,0.25),
    inset 0 0 60px rgba(255,255,255,0.18);

  animation: orbFloat 10s ease-in-out infinite;
}

.ring {
  position: absolute;

  border-radius: 50%;
  border: 1px solid rgba(255,255,255,0.12);

  backdrop-filter: blur(8px);
}

.ring-1 {
  width: 520px;
  height: 520px;

  animation:
    rotateSlow 18s linear infinite;
}

.ring-2 {
  width: 620px;
  height: 620px;

  border-color: rgba(126,240,214,0.08);

  animation:
    rotateSlowReverse 24s linear infinite;
}

@keyframes orbFloat {
  0% {
    transform: translateY(0px);
  }

  50% {
    transform: translateY(-18px);
  }

  100% {
    transform: translateY(0px);
  }
}

@keyframes rotateSlow {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}

@keyframes rotateSlowReverse {
  from {
    transform: rotate(360deg);
  }

  to {
    transform: rotate(0deg);
  }
}
</style>