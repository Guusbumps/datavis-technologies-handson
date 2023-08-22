<script>
    // Dimensions
    const [height, width] = [400, 600];
    const margin = { top: 50, right: 5, bottom: 55, left: 50 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;

    export let data = [];

    import { select } from "d3-selection";
    import { scaleLinear, scaleLog, scaleOrdinal } from 'd3-scale';
    import { schemeTableau10 } from 'd3-scale-chromatic';
    import { axisLeft, axisBottom} from 'd3-axis';

    const xscale = scaleLog().domain([300,150000]).range([0, innerWidth]);
    const yscale = scaleLinear().domain([0,100]).range([innerHeight, 0]);
    const cscale = scaleOrdinal(schemeTableau10).domain(data.map((d) => d.continent))
    const rscale = scaleLinear().domain([0,1400000000]).range([3,40])

    const yAxis = (node) => axisLeft(yscale)(select(node));
    const xAxis = (node) => axisBottom(xscale)(select(node));
  </script>
  
  <svg viewBox="0 0 {width} {height}" style="max-width: {width}px">
    <g transform="translate({margin.left}, {margin.top})">
      {#each data as d}
        {#if d.income && d.life_exp}
          <circle 
            cx={xscale(+d.income)} 
            cy={yscale(+d.life_exp)} 
            r={rscale(+d.population)}  
            fill={cscale(d.continent)}
          >
          </circle>
        {/if}
      {/each}
    </g>
    <g use:xAxis></g>
    <g use:yAxis></g>
  </svg>
  