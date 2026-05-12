<script>
  let { children } = $props();
</script>

<div class="container">
  {@render children()}
</div>

<style>
.container {
  width: 100%;
  max-width: 1100px;
}
</style>