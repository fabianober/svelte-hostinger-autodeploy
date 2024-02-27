<script>
    let counter = 0;

    function increment() {
        counter += 1;
    }

</script>

<h1>Welcome to my first Svelte-Page.</h1>
<button on:click={increment}>Clicked {counter} times</button>

<br><br>
<a href="/about">Go to about</a>
<br><br>
Go to <a href="https://fabian-ober.de">Fabian Ober</a> to see more.