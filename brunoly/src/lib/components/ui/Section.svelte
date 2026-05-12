<script>
  let { children } = $props();
</script>

<div class="section">
  {@render children()}
</div>

<style>
.section {
  padding: var(--s-5) 0;
  display: flex;
  justify-content: center;
}
</style>