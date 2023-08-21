<script>
  let current = "";
</script>

<!-- We will cover buttons later on! -->
<button 
  class="btn btn-secondary" 
  class:lastClicked={current === "messi"}
  on:click={() => (current = "messi")}>
  Messi
</button>

<button 
  class="btn btn-secondary" 
  class:lastClicked={current === "ronaldo"}
  on:click={() => (current = "ronaldo")}>
  Ronaldo
</button>

<button 
  class="btn btn-secondary" 
  class:lastClicked={current === "neymar"}
  on:click={() => (current = "neymar")}>
  Neymar
</button>

<style>
  .lastClicked {
    background-color: red;
  }
</style>