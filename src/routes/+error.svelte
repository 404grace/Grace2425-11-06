<script>
	import { page } from '$app/stores';
</script>

<h1>Pazi ga! {$page.status}: {$page.error?.message}</h1>
