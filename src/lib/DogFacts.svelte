<script>
  let fact = '';
  const fetchDogFact = () => {
    fetch('https://dogapi.dog/api/v2/facts')
      .then((res) => res.json())
      .then((jsonData) => {
        fact = jsonData.data.map((f) => f.attributes.body);
      });
  };
</script>

<button on:click={fetchDogFact}>Fetch a dog fact</button>

<p>{fact}</p>
