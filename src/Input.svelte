<script>
  let value = ''
  let response = []

  const handleInput = (event) =>
    value = event.target.value

  $: if (value.length > 2) {
    fetch(`https://www.omdbapi.com/?s=${value}&apikey=422350ff`)
      .then(res => res.json())
      .then(apiResponse => {
        response = apiResponse.Search
      })
  }
</script>

<input value={value} on:input={handleInput} />