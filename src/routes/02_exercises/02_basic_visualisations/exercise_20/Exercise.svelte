<script>
    // Dimensions
    const width = 600;
    const height = 300;
    const margin = { top: 10, right: 10, bottom: 30, left: 60 };
    const innerWidth = width - margin.left - margin.right;
    const innerHeight = height - margin.top - margin.bottom;

    import { scaleLinear } from 'd3-scale'
    import { scaleOrdinal } from 'd3-scale'

    // Array
    const data = [
      { service: "Netflix", viewers: 2.9 },
      { service: "Amazon Prime Video", viewers: 1.3 },
      { service: "Disney+", viewers: 2.1 },
      { service: "Hulu", viewers: 0.9 },
      { service: "Apple TV", viewers: 1.1 },
      { service: "Rakuten", viewers: 0.4 }
    ];

    const xscale = scaleBand().domain(data.map((d) => d.service)).range([0, innerWidth]).padding(0.2);
    const yscale = scaleLinear().domain(0, 4).range(0, innerHeight)

  </script>
  
  <!-- setting a viewBox and max-width allows the SVG to shrink but not grow! -->
  <svg viewbox="0 0 {width} {height}" style="max-width: {width}px">
    <g transform={`translate(${margin.left},${margin.top})`}>
      {#each data as d}
        <rect
          x = {xscale(d.service)}
          y = {yscale(d.viewers)}
          width = 1
          height = {yscale(d.viewers)}
        />
      {/each}
    </g>
  </svg>
  