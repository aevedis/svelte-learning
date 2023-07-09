<script>
  export let initialCount = undefined;
  export let maxCount = undefined;
  let count = initialCount;

  console.log($$props, $$restProps);

  function increment() {
    if (count === maxCount) {
      return;
    }
    count += 1;
    console.log(count);
  }

  function decrement() {
    if (count === 0) {
      return;
    }
    count -= 1;
    console.log(count);
  }

  $: string = `${count} laps`;
</script>

<h1>{string}</h1>
<div>
  <button id="increment" on:click={increment}>Increment</button>
  <button id="decrement" on:click={decrement}>Decrement</button>
</div>

<style>
  div {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  button {
    background-color: darkgreen;
    color: #fff;
    border: green 1px solid;
    padding: 10px 20px;
    margin: 3px;
    border-radius: 5px;
    cursor: pointer;
  }

  button:hover {
    background-color: #00cc00;
  }

  #decrement {
    background-color: darkred;
    border: red 1px solid;
    color: white;
  }

  #decrement:hover {
    background-color: #cc0000;
  }

  h1 {
    color: #444;
    font-family: sans-serif;
    font-size: 4em;
    text-align: center;
  }
</style>
