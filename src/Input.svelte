<script>
  let value = ''
  let loading = false
  let response = []

  const handleInput = (event) =>
    value = event.target.value

  $: if (value.length > 2) {
    loading = true
    fetch(`https://www.omdbapi.com/?s=${value}&apikey=422350ff`)
      .then(res => res.json())
      .then(apiResponse => {
        response = apiResponse.Search || []
        loading = false
      })
  }
</script>

<input
  placeholder="Search movies..."
  value={value}
  on:input={handleInput}
/>

{#if loading}
  <strong>Loading...</strong>
{:else}
  {#if response.length > 0}
    <strong>Tenemos {response.length} películas</strong>
  {:else}
    <strong>No hay resultados</strong>
  {/if}
{/if}
