<script>
  let text = '';
  export let addText;

  const textTyped = () => {
    if (text.length === 0) return;

    addText(text);
    text = '';
  };
</script>

<input type="text" bind:value={text} />
<button on:click={textTyped}>Add text</button>
