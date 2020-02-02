<script>
	export let initialCounter = 0;
	let contador = initialCounter

	function handleClick () {
		contador++
	}
</script>

<style>
	span {
		color: red;
	}
</style>

<button on:click={handleClick}>Incrementar</button>
<span>{contador}</span>