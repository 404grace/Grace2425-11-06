<script lang="ts">
	import { page } from '$app/stores';
	import '../app.css';
</script>

<nav class="w-full p-6 bg-orange-300">
	<div class="flex gap-4">
		<a href="/" class={$page.url.pathname === '/' ? 'font-bold' : ''}>Gumb</a>
		<a href="/domov" class={$page.url.pathname === '/domov' ? 'font-bold' : ''}>Domov</a>
		<a href="/trgovina" class={$page.url.pathname === '/trgovina' ? 'font-bold' : ''}>Trgovina</a>
		<a href="/kalkulator" class={$page.url.pathname === '/kalkulator' ? 'font-bold' : ''}
			>Kalkulator</a
		>
		<a href="/todo" class={$page.url.pathname === '/todo' ? 'font-bold' : ''}>Zadolžitve</a>
		<a href="/stevila" class={$page.url.pathname === '/stevila' ? 'font-bold' : ''}>Števila</a>
		<a href="/posts" class={$page.url.pathname === '/posts' ? 'font-bold' : ''}>Posts</a>
		<a href="/novoletne" class={$page.url.pathname === '/novoletne' ? 'font-bold' : ''}>Novoletne</a
		>
		<a href="/yearbook" class={$page.url.pathname === '/yearbook' ? 'font-bold' : ''}>Yearbook</a>
	</div>
</nav>

<div class="w-full h-screen bg-slate-400">
	<slot />
</div>
