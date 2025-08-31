<script>
  let count = $state(0);
</script>

<main>
  <h1>Hello World</h1>
  <button onclick={() => count++}>
    clicks: {count}
  </button>
</main>

<style>
  h1 {
    color: red;
  }
</style>
