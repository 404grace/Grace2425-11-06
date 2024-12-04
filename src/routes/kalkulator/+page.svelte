<script lang="ts">
	type Operator = '+' | '-' | '*' | '/';
	let num1 = 0;
	let num2 = 0;
	let op: Operator = '+';
	let result = 0;
	$: {
		if (op === '+') {
			result = num1 + num2;
		} else if (op === '-') {
			result = num1 - num2;
		} else if (op === '*') {
			result = num1 * num2;
		} else if (op === '/') {
			result = num1 / num2;
		}
	}
	function randomNumber() {
		num1 = Math.floor(Math.random() * 100);
		num2 = Math.floor(Math.random() * 100);
	}
</script>

<div class="p-4">
	<h1 class="text-4xl">Kalkulator</h1>
	<div class="flex flex-col gap-10">
		<div class="flex flex-row justify-center gap-3">
			<input
				class="border-green-500 border-4 p-2 rounded-full text-center h-20 text-4xl"
				bind:value={num1}
				type="number"
				placeholder="0"
			/>

			<select
				class="border-green-500 border-4 p-2 rounded-full text-center w-20 h-20 text-4xl"
				bind:value={op}
			>
				<option value="+">+</option>
				<option value="-">-</option>
				<option value="*">*</option>
				<option value="/">/</option>
			</select>
			<input
				class="border-green-500 border-4 p-2 rounded-full text-center h-20 text-4xl"
				bind:value={num2}
				type="number"
				placeholder="0"
			/>
			<button
				on:click={randomNumber}
				class="bg-green-500 hover:bg-green-900 font-bold text-4xl p-1 w-20 h-20 rounded-full text-white"
				>?</button
			>
		</div>
		<div class="flex flex-row justify-center">
			<p class="text-8xl">{num1} {op} {num2} = {result}</p>
		</div>
	</div>
</div>
