<script lang="ts">
	/**
	 * NALOGA:
	 * - Poglej v data.ts; tam bos nasel seznam categories (ki je tu ze importan)
	 * - V grid-u s tremi stolpci prikazi vse kategorije s karticami (uporabi komponento Card)
	 * - Vsaka kartica naj ima: Naslov, Opis, Sliko
	 *
	 * DODATNA NALOGA:
	 * - Na telefonu (oz majhnem ekranu) naj se kartice prikazejo v 1 stolpcu
	 *  (Pomoč: https://tailwindcss.com/docs/responsive-design)
	 */

	import { categories } from './data';
	import Card from './Card.svelte';
</script>

<div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-3">
	{#each categories as category}
		<Card {category}></Card>
	{/each}
</div>
