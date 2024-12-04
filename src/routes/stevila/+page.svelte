<script lang="ts">
	let stevilo = 3;
	let sodo: boolean;
	let seznamDeliteljev: number[] = [];
	let vsota = 0;

	function jeSodo(num: number) {
		// preverimo kakšen je ostanek pri deljenju števila num z 2
		// če je ostanek == 0 --> je število sodo, v nasprotnem primeru pa je liho;
		return num % 2 == 0;
		// if (num % 2 == 0) return true;
		// return false;
	}

	// napiši funkcijo izpisiDelitelje(num), ki vrne [] seznam v katerem bodo
	// vsi delitelji števila

	function izpisiDelitelje(num: number) {
		let delitelji: number[] = [];
		for (let i = 1; i < num; i++) {
			if (num % i == 0) delitelji.push(i);
		}
		return delitelji;
	}

	// napiši funkcijo, ki izračuna vsoto deliteljev števila

	function vsotaDeliteljev(nums: number[]) {
		let sestevek = 0;
		for (const i of nums) {
			sestevek += i;
		}

		return sestevek;
	}

	$: {
		sodo = jeSodo(stevilo);
		seznamDeliteljev = izpisiDelitelje(stevilo);
		vsota = vsotaDeliteljev(seznamDeliteljev);
	}
</script>

<div class="flex flex-col gap-10 items-center justify-center min-h-screen">
	<div>
		<input
			min="0"
			bind:value={stevilo}
			class="border-4 border-green-500 rounded-full text-center text-4xl p-4"
			type="number"
		/>
	</div>
	<div class="grid grid-cols-4 gap-4">
		<div class="bg-green-500 rounded-xl p-2">
			<p class="text-white text-4xl">Število je:</p>
			<p class="text-white text-6xl">{sodo ? 'sodo' : 'liho'}</p>
		</div>
		<div class="bg-green-500 rounded-xl p-2">
			<p class="text-white text-4xl">Seznam deliteljev:</p>
			<ul class="flex flex-wrap gap-2">
				{#each seznamDeliteljev as st}
					<li class="bg-white p-2 rounded-xl">{st}</li>
				{/each}
				<li class="bg-white p-2 rounded-xl">{stevilo}</li>
			</ul>
		</div>
		<div class="bg-green-500 rounded-xl p-2">
			<p class="text-white text-4xl">Vsota deliteljev je:</p>
			<p class="text-white text-6xl">{vsota}</p>
		</div>
		<div class="bg-green-500 rounded-xl p-2">
			<p class="text-white text-4xl">Število je popolno:</p>
			<p class="text-white text-6xl">{vsota == stevilo ? '✅' : '❌'}</p>
		</div>
	</div>
</div>
