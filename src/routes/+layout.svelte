<script>
	import Menu from '../lib/Menu.svelte';
	import '../app.css';
</script>

<!-- all inside a div -->
<div class="flex flex-col h-screen">
	<Menu />
	<slot />
</div>
