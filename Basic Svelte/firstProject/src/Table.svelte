<script>
	let people = [
		{name: 'sigma', color:'red', age:4, id:1},
		{name: 'skibidi', color:'orange', age:3, id:2},
		{name: 'sukri', color:'blue', age:44, id:3},
	];

	const deleteClick = (id) => {
		people = people.filter((person) => {
			return person.id != id
		})
		
	}

	let num = 1;

</script>

{#if num > 20}
	<p>Nothing to see here</p>

	{:else if num > 5}
	<p>So close a little bit more ...</p>
	{:else}

<main>

<div>

<!-- For Each Loop // person.id to give unique value for each-->
	{#each people as person (person.id)}
	<div style="color : {person.color}">
		<h5>Nama Saya : {person.name}</h5>
		<p>Umur Saya : {person.age}</p>
		<button on:click={() => deleteClick(person.id)}>Delete</button>
	</div>
	{:else}
	<p>No people to show</p>
	{/each}


</div>


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
{/if}
