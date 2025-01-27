<script lang="ts">
	import Page from '../+page.svelte';
	export let animal;
	export let addToWatchlist: (name: string) => void;
</script>

<div
	class="bg-red-300 p-5 text-center rounded-xl border border-black sm:bg-orange-600 md:bg-sky-900"
>
	<h1 class="text-4xl text-red-600 text-center">{animal.name}</h1>
	<p>{animal.latinName}</p>
	<img src={animal.photo} alt={animal.name} />
	<p>{animal.weight}</p>
	<p>{animal.lifespan}</p>
	<p>{animal.class}</p>
	<button
		class="bg-violet-500 rounded-full text-white px-2"
		on:click={() => addToWatchlist(animal.name)}>Add to watchlist</button
	>
</div>
