<section class="about">
  <div class="card">
    <h2>Sobre mim</h2>

    <p>
      Eu construo sistemas, interfaces e narrativas digitais.
      Misturo programação com estética, lógica com sensação.
    </p>

    <p>
      Gosto de pensar tecnologia como linguagem criativa —
      não só ferramenta.
    </p>

    <div class="tags">
      <span>Frontend</span>
      <span>Backend</span>
      <span>Design</span>
      <span>Música</span>
      <span>Storytelling</span>
    </div>
  </div>
</section>

<style>
.about {
  padding: var(--s-5) 0;
  display: flex;
  justify-content: center;
}

.card {
  max-width: 800px;

  background: var(--glass-mid);
  backdrop-filter: blur(var(--blur-lg));

  padding: var(--s-4);
  border-radius: var(--r-md);

  border: 1px solid var(--glass-border);
}

h2 {
  font-size: 2rem;
  margin-bottom: var(--s-3);
}

.tags {
  margin-top: var(--s-3);
  display: flex;
  gap: var(--s-1);
  flex-wrap: wrap;
}

span {
  padding: 0.4rem 0.8rem;
  border-radius: var(--r-lg);
  background: rgba(125,220,255,0.1);
}
</style>