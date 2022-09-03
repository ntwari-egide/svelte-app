<script>
	import {fade,fly} from 'svelte/transition'

	import {randomStore} from './store'

	export let name;


	let rando;

	let randos = []

	// use effect in svelte, calculate each time app starts

	$: result = Math.round(rando) ? 'Winner' : 'Loser';

	$: firstname = 'Egide'
	$: phoneNumber = "1234567890"

	function setRando() {
		rando  = Math.random()
		randos = [...randos, rando]
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

	<!-- if rando is less than 100 -->

	{#if rando < 50}
		<p transition:fade>Less than 50</p>
	{/if}

	<!-- if rando is greater than 100 -->

	{#if rando > 50}
		<p transition:fly>Greater than 50</p>
	{/if}

	<ul>
		{
			#each randos as rand }
				<p>{rand}</p>
			{/each
		}
	</ul>

	<hr>
	<h2>STORES CONCEPT</h2>

	<p>{$randomStore}</p>

	<button on:click={()=> randomStore.set(Math.random())}>UPDATE STORE</button>


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