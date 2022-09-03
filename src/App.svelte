<script>
	export let name;

	let rando;

	// use effect in svelte, calculate each time app starts

	$: result = Math.round(rando) ? 'Winner' : 'Loser';

	$: firstname = 'Egide'
	$: phoneNumber = "1234567890"

	function setRando() {
		rando  = Math.random()
	}
</script>

<main>
	
	<h1>Hello {name}!</h1>

	<h2>Random : {rando}</h2>

	<h3><strong>My name: {firstname}</strong></h3>

	<p>{ result }</p>
	<p>{ result }</p>

	<button on:click={setRando}>GENERATE</button>

	<h2>Value Binding, and dynamic binding</h2>
	
	<input type="text" bind:value={firstname}>

	

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