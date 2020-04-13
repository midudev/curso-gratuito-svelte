<script>
  export let title, poster, year
</script>

<style>
article {
  border: 1px solid #eee;
  border-radius: 4px;
  margin-bottom: 8px;
  padding: 16px;
}

h3 {
  font-size: 24px;
  margin-bottom: 4px;
}
</style>

<article>
  <img alt={title} src={poster} />
  <h3>{title}</h3>
  <span>{year}</span>
  {#if 2020 - year < 5}
    <i>🆕</i>
  {/if}
</article>