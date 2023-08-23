<script>
  // Properties
  export let year = 0;
  export let data = [];
  let interval = 0;
  const continents = ["europe", "asia", "americas", "africa"];

  function start() {
    interval = setInterval(step, 50);
  }

  function stop() {
    clearInterval(interval)
  }

  function step() {
    year += 1
  }

</script>

<div class="row">
  <!--  -->
  <button on:click={start}>start</button>
  <button on:click={stop}>stop</button>
  {year}
  {data}
</div>
