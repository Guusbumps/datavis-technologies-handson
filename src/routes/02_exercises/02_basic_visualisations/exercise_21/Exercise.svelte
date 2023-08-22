<script>
    import {csv} from 'd3-fetch';
    import Scatterplot from './Scatterplot.svelte';
    
    let data = null;
    onMount(async () => {
        console.log("onMount started!");
        data = await csv('/data/gapminder.json');
        console.log("Data loaded!");
    });
    console.log("Script finished!")


</script>
