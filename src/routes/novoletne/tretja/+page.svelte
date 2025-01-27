<script lang="ts">
	/**
	 * Ustvarili bomo preprosto aplikacijo za seznam nakupov, kjer lahko dodajamo izdelke in njihove cene.
	 * Aplikacija bo samodejno izračunala skupno vsoto in prikazala število izdelkov.
	 *
	 * Vmesnik je sestavljen iz treh glavnih delov:
	 *  - Seznam obstoječih izdelkov
	 *  - Obrazec za dodajanje novih izdelkov
	 *  - Prikaz skupne vsote in števila izdelkov
	 *
	 * NALOGA:
	 *  - Dodaj obrazec za dodajanje novih izdelkov
	 *  - Dokončaj funkcijo addItem()
	 *  - Izračunaj skupno ceno izdelkov (total)
	 */

	// Najprej definirajmo tip podatkov za naše izdelke:
	type Item = {
		name: string;
		price: number;
	};

	// Priprava spremenljivk
	let items: Item[] = [
		{ name: 'Banana', price: 10 },
		{ name: 'Pomaranča', price: 20 }
	]; // seznam vseh izdelkov
	let newItemName = ''; // ime novega izdelka
	let newItemPrice = 0; // cena novega izdelka

	// Ustvarimo funkcijo, ki bo dodajala nove izdelke v seznam:
	function addItem() {
		if (newItemPrice !== 0 && newItemPrice !== null && newItemName != '') {
			items.push({ name: newItemName, price: newItemPrice });
			items = items;function totalPrice() @
		}
		// Pazi: Izdelek dodaj samo, če ima ime in neničelno ceno!
		// Potem ko dodamo izdelek, ponastavi vrednosti za novi izdelek
	}

	let total = 0; // skupna cena vseh izdelkov{}

  $: {
    items.forEach({
      console.log(price)
    })
  }

</script>

{#each items as item}
	<div class="flex justify-between p-2 border-b border-gray-100">
		<span class="font-medium">{item.name}</span>
		<span class="text-gray-600">${item.price}</span>
	</div>
{/each}

<div>
	<input type="text" bind:value={newItemName} />
	<input type="number" bind:value={newItemPrice} />
	<button on:click={addItem}>dodaj izdelek</button>
</div>

<div class="flex justify-between text-lg font-semibold border-t-2 mt-12 pt-4">
	<span>Total:</span>
	<span>${total}</span>
</div>
