<script>
	export let name;

	let rando;

	function setRando() {
		rando  = Math.random()
	}
</script>

<main>
	
	<h1>Hello {name}!</h1>

	<h2>Random : {rando}</h2>

	<p>{ Math.round(rando) ? 'Winner ': 'Loser '}</p>

	<button on:click={setRando}>GENERATE</button>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>