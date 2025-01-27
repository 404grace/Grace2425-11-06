<script lang="ts">
	import type { Category } from './data';

	export let category: Category;
</script>

<div class="bg-red-300 p-5 rounded-xl border border-black sm:bg-orange-600 md:bg-sky-900">
	<div>
		<h1>{category.name}</h1>
	</div>
	<div>
		<img src={category.image} />
		<p>{category.description}</p>
	</div>
</div>
