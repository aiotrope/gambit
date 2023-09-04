<script>
  let numbers = [];
  let number;
  const addNumber = () => {
    numbers = [...numbers, number];
    number = ''
    
  };

  let sum;

  $: sum = () =>
    numbers.reduce((total, current) => {
      return total + current;
    }, 0);

  let len = numbers.length;

  $: len = numbers.length;

  let average;

  $: average = len !== 0 ? sum() / len : 0;
</script>

<h1>Statistics generator</h1>

<input type="number" bind:value={number} />
<button on:click={addNumber}>Add value</button>

<h2>Statistics</h2>
<p>Sum: {sum()}</p>
<p>Total numbers: {len}</p>
<p>Average: {average}</p>

<h2>Numbers entered so far</h2>

<ul>
  {#each numbers as num}
    <li>{num}</li>
  {/each}
</ul>
