<script>
	import '../app.css';
	import Nav from '$lib/Nav.svelte';
</script>

<div class="p-8 max-w-6xl mx-auto">
	<Nav class="flex justify-center w-full" />
	<slot />
</div>
