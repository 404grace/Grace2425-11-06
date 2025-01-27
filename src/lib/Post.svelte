<script lang="ts">
	import type { UserPost } from '$lib';
	import { Heart } from 'lucide-svelte';

	export let post: UserPost;
</script>

<div class="font-bold">{post.text}</div>
<Heart />
