<script>
    let count = 0
    function add(event) {
        count += 1
        console.log("Clicked!");
        }
    function reset(event) {
        count = 0;
        console.log("Clicked!");
    }
</script>

<button class="btn btn-primary" on:click={add}>add</button>
<button class="btn btn-primary" on:click={reset}>reset</button>

<span>
Number of times clicked = {count}
</span>