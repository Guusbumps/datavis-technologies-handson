<script>
    // Dimensions
    const [height, width] = [400, 600];
    const margin = { top: 50, right: 5, bottom: 55, left: 50 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;

    export let data = []

    import { scaleLinear } from 'd3-scale'
    const xscale = scaleLinear().domain(0,100000).range(0, innerWidth)
    const yscale = scaleLinear().domain(0,100).range(0, innerHeight)
  </script>
  
  <svg viewBox="0 0 {width} {height}" style="max-width: {width}px">
    <g transform="translate({margin.left}, {margin.top})">
      {#each data as d}
        <circle cx={xscale(d.income)} cy={yscale(d.life_exp)} r=10/>
      {/each}
    </g>
  </svg>
  