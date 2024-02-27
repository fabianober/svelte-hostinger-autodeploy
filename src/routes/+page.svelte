<script>
    let counter = 0;

    function increment() {
        counter += 1;
    }

    let userInput = "";

  const handleSubmit = () => {
    window.location.href = `/blog/${encodeURIComponent(userInput)}`;
  };

</script>

<h1>Welcome to my first Svelte-Page.</h1>
<button class="bg-blue-500 hover:bg-blue-400 text-white font-bold py-2 px-4 border-b-4 border-blue-700 hover:border-blue-500 rounded" on:click={increment}>Clicked {counter} times</button>


<br><br>
<a href="/about">Go to about</a>
<br><br>
<a href="/blog/1">Go to blog 1</a><br>
<a href="/blog/2">Go to blog 2</a><br>
<a href="/blog/3">Go to blog 3</a><br>
<br>
<h1>Go to any blog you like</h1><br>
<input bind:value={userInput} placeholder="Enter text" />
<button class="bg-blue-500 hover:bg-blue-400 text-white font-bold py-2 px-4 border-b-4 border-blue-700 hover:border-blue-500 rounded" on:click={handleSubmit}>Go to any blog you like</button>
<br><br>
Go to <a href="https://fabian-ober.de">Fabian Ober</a> to see more.