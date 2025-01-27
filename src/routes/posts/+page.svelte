<script lang="ts">
	import type { UserPost } from '$lib';
	import Post from '$lib/Post.svelte';

	let posts: UserPost[] = [
		{ text: 'Hello World!', timestamp: Date.now(), likes: 0 },
		{ text: 'Hello Slovenia!', timestamp: Date.now(), likes: 0 }
	];
</script>

{#each posts as p}
	<Post post={p} />
{/each}
