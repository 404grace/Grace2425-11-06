<script lang="ts">
	let besedilo = '';
	let dolzina = 0;
	let maxDolzina = 300;

	function urediBesedilo(f: string) {
		switch (f) {
			case 'velike':
				besedilo = besedilo.toUpperCase();
				break;
			case 'male':
				besedilo = besedilo.toLowerCase();
				break;
		}
	}

	function nakljucnaBarva() {
		let barva = ['blue', 'orange', 'yellow', 'red', 'purple'];
		let moc = [500, 600, 700, 800, 900];

		return (
			'text-' +
			barva[Math.floor(Math.random() * barva.length)] +
			'-' +
			moc[Math.floor(Math.random() * moc.length)]
		);
	}

	$: {
		dolzina = besedilo.length;
	}
</script>

<div class="flex flex-col items-center justify-center min-h-screen gap-4">
	<h3 class="text-blue-500 text-4xl">Besedilko</h3>
	<textarea
		maxlength={maxDolzina}
		bind:value={besedilo}
		class="w-1/2 border-4 border-blue-500 rounded-lg"
	></textarea>
	<div class="grid grid-cols-3 gap-4">
		<button on:click={() => urediBesedilo('velike')} class="bg-blue-500 text-white rounded-full p-4"
			>Velike črke</button
		>
		<button on:click={() => urediBesedilo('male')} class="bg-blue-500 text-white rounded-full p-4"
			>Male črke</button
		>
		<p>{dolzina}/{maxDolzina}</p>
	</div>
	<div class="flex flex-wrap w-1/2 gap-1">
		{#each besedilo.split(' ') as beseda}
			<span class={nakljucnaBarva()}>{beseda}</span>
		{/each}
	</div>
</div>
