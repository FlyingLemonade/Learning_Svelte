<script>
	let firstName = "Yoshi";
	let lastName = "Sukri"
	let color = "Black"

	// REACTIVE VARIABLE
	$: fullName = `${firstName} ${lastName}`;
	$: {console.log(color);
		console.log(fullName);
	}


	
	const handleClick = () => {
		firstName = "Sukri"

	}

	const handleInput = (e) =>{
		firstName = e.target.value
	}
</script>

<main>
	<h1 style="color: {color}">Hello {fullName}!</h1>
	<!-- <button on:click={handleClick} >Not Your firstName?</button> -->
	
	<!-- LONG WAY -->
	<!-- <input type="text" on:input={handleInput} value={firstName}> -->
	
	<!-- SHORTER WAY -->
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
	<input type="text" bind:value={color}>


	<!-- REACTIVE VALUE -->






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