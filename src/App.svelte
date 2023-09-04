<script>
  let list = ['Never', 'gonna', 'give', 'you', 'up'];
  let index = 0;
  const maxIndex = list.length - 1

  const updateIndex = () => {
    if (index === maxIndex) {
      index = 0
    } else {
      index++
    }
  };
</script>

<h1>{list[index]}</h1>
<p>Elements: {index}</p>
<button on:click={updateIndex}>Next!</button>
