<nav class="navbar">
  <div class="logo">Brunão</div>

  <div class="links">
    <a href="#projects">Projetos</a>
    <a href="#about">Sobre</a>
    <a href="#blog">Blog</a>
    <a href="#contact">Contato</a>
  </div>
</nav>

<style>
  .navbar {
    position: fixed;

    top: 1.5rem;
    left: 50%;

    transform: translateX(-50%);

    width: 80%;

    display: flex;
    justify-content: space-between;
    align-items: center;

    padding: 1rem 1.5rem;

    border-radius: 999px;

    background: var(--glass-soft);

    backdrop-filter: blur(20px);

    border: 1px solid var(--glass-border-soft);

    z-index: 1000;
  }

  .logo {
    font-weight: 700;
    letter-spacing: 0.04em;
  }

  .links {
    display: flex;
    gap: 2rem;
  }

  a {
    color: white;
    text-decoration: none;

    opacity: 0.8;

    transition:
      opacity 0.3s ease,
      transform 0.3s ease;
  }

  a:hover {
    opacity: 1;
    transform: translateY(-2px);
  }
</style>