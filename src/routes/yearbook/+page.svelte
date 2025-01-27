<script lang="ts">
	import { animals, type Animal } from './animals';
	import AnimalCard from './AnimalCard.svelte';
	let searchAnimal: string = '';
	let filteredAnimals: Animal[] = [];
	let classOptions: string[] = [];
	let searchClass: string = 'all';
	let watchlist: string[] = [];

	$: {
		for (let animal of animals) {
			if (!classOptions.includes(animal.class)) {
				classOptions.push(animal.class);
			}
		}
	}

	function searchByName(name: string) {
		filteredAnimals = animals.filter((animal) =>
			animal.name.toLowerCase().includes(name.toLowerCase())
		);
	}

	function searchByClass(search: string) {
		if (search !== 'all') {
			filteredAnimals = animals.filter((animal) => animal.class === search);
		} else {
			filteredAnimals = animals;
		}
	}

	function addToWatchlist(name: string) {
		watchlist = [...watchlist, name];
	}

	$: {
		searchByName(searchAnimal);
	}

	$: {
		searchByClass(searchClass);
	}
</script>

<h1 class="text-center text-5xl">ANIMALS!!!</h1>
watchlist:
<div class="flex gap-2"><p>{watchlist}</p></div>
<div class="flex flex-cols justify-center items-center">
	<p>Išči po imenu:</p>
	<input
		class="rounded-xl m-2 p-2"
		placeholder="Search animal by name"
		type="text"
		bind:value={searchAnimal}
	/>
	<p>Išči po razredu:</p>
	<select bind:value={searchClass}>
		<option value="all">All</option>
		{#each classOptions as option}
			<option value={option}>{option}</option>
		{/each}
	</select>
</div>
<div class="grid sm:grid-cols-3 grid-cols-1 justify-center gap-2">
	{#each filteredAnimals as animal}
		<AnimalCard {animal} {addToWatchlist} />
	{/each}
</div>
