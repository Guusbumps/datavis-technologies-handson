<script>
  // Properties
  export let data = [];
  export let year = 0;
  export let selected_continent = "all";
  const continents = ["europe", "asia", "americas", "africa"];  
  let interval = 0;
 
  function start() {
    interval = setInterval(step, 50);
  }

  function stop() {
    clearInterval(interval)
  }

  function step() {
    year = (year + 1) % data.length;
  }

</script>

<div class="row">
  <!--  -->
  <button on:click={start}>start</button>
  <button on:click={stop}>stop</button>
  {year}
</div>
