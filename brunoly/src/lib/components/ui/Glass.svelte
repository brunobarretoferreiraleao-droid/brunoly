<script>
  let { children } = $props();
</script>

<div class="glass">
  {@render children()}
</div>
<style>
.glass {
  background: var(--glass);
  border: 1px solid var(--glass-border);
  backdrop-filter: blur(var(--blur-md));
  border-radius: var(--r-md);
  padding: var(--s-3);
}
</style>