<section class="hero">
  <div class="content">
    <p class="eyebrow">Criatividade arquitetada.</p>

    <h1>
      Transformando ideias
      em experiências.
    </h1>

    <p class="description">
      Programação, design, música,
      storytelling e interfaces vivas.
    </p>

    <button>
      Explore meu universo digital.
    </button>
  </div>

  <div class="orb"></div>
</section>

<style>
  .hero {
    min-height: 100vh;

    display: flex;
    justify-content: center;
    align-items: center;

    position: relative;

    overflow: hidden;
  }

  .content {
    text-align: center;

    z-index: 2;

    max-width: 900px;

    padding: 2rem;
  }

  .eyebrow {
    color: #7ddcff;

    text-transform: uppercase;

    letter-spacing: 0.2em;

    margin-bottom: 1rem;
  }

  h1 {
    font-size: clamp(3rem, 8vw, 7rem);

    line-height: 0.95;

    margin: 0;

    font-weight: 700;
  }

  .description {
    margin-top: 1.5rem;

    font-size: 1.2rem;

    opacity: 0.75;

    line-height: 1.7;
  }

  button {
    margin-top: 2rem;

    border: none;

    padding: 1rem 1.8rem;

    border-radius: 999px;

    background: rgba(255,255,255,0.08);

    backdrop-filter: blur(20px);

    color: white;

    cursor: pointer;

    transition:
      transform 0.3s ease,
      background 0.3s ease;
  }

  button:hover {
    transform: translateY(-4px);

    background: rgba(255,255,255,0.14);
  }

  .orb {
    position: absolute;

    width: 500px;
    height: 500px;

    border-radius: 50%;

    background:
      radial-gradient(circle at 30% 30%,
      rgba(125,220,255,0.7),
      rgba(96,165,250,0.15));

    filter: blur(40px);

    animation: float 8s ease-in-out infinite;
  }

  @keyframes float {
    0% {
      transform: translateY(0px);
    }

    50% {
      transform: translateY(-30px);
    }

    100% {
      transform: translateY(0px);
    }
  }
</style>