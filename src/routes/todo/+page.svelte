<script lang="ts">
	type Task = {
		text: string;
		status: boolean;
	};

	let newTask: string = '1234';

	let tasks: Task[] = [
		{
			text: 'Skuham kosilo',
			status: true
		},
		{
			text: 'Zložim nogavice v omaro',
			status: false
		},
		{
			text: 'Kupim novo gumo za kolo',
			status: true
		}
	];

	function add() {
		tasks = [
			...tasks,
			{
				text: newTask,
				status: false
			}
		];

		newTask = '';
	}
</script>

<div class="flex justify-center">
	<div class="bg-teal-200 w-6/12 rounded-2xl m-4 p-4">
		<div class="flex gap-2">
			<input bind:value={newTask} class="bg-green-200 rounded-full" type="text" />
			<button on:click={add} class="bg-green-900 rounded-full text-white px-4"
				>Dodaj zadolžitev</button
			>
		</div>

		<h3 class="text-4xl">Zadolžitve</h3>
		<!--zanka, ki gre čez vse elemente seznama "tasks" in izpiše posamezen task, kot <p></p>-->

		{#each tasks as task}
			<p>
				<button
					class={task.status ? 'bg-green-900' : 'bg-red-900'}
					on:click={() => (task.status = !task.status)}>{task.status ? '✅' : '❌'}</button
				><span class={task.status ? 'underline' : 'line-through'}>{task.text}</span>
			</p>
		{/each}
	</div>
</div>
