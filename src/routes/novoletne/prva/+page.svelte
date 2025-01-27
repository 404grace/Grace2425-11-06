<script lang="ts">
	function randomNum() {
		num = Math.floor(Math.random() * 100000000);
	}
	function jeSodo(num: number) {
		// if (num % 2 == 0) return true;
		// else return false;
		return num % 2 == 0;
	}
	let num = 0;

	/**finiraj spremenljivko "num" in jo "poveži" z <input> (Nasvet: uporabi bind:value)
	 *  - Če je num sodo, izpiši "Število je sodo", če je liho, izpiši "Število je liho"
	 *
	 * DODATNA NALOGA:
	 *  - Dodaj <button> s tekstom "Random"
	 *  - Po kliku na "Random" naj se num nastavi na naključno število med 1 in 100000000
	 */
</script>

<input bind:value={num} type="number" />
<p>število je {jeSodo(num) ? 'sodo' : 'liho'}</p>

<button on:click={randomNum}>Random</button>
