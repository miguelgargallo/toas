<script>
	// @ts-nocheck

	import Toas from '$lib/Toas.svelte';
	import { onMount } from 'svelte';
	import Footer from '../lib/Footer.svelte';

	function ToasSuccess() {
		window['showToas']('Operation Successful', 'success');
	}
	function ToasError() {
		window['showToas']('Operation Failed', 'error');
	}
	function ToasLoading() {
		window['showToas']('Loading...', 'loading');
	}

	onMount(() => {
		window['showToas']('🍞 Welcome to Toas', 'onmount');
	});
</script>

<Toas />

<div class="flex flex-col space-y-8 p-8 items-center text-white justify-center h-screen bg-black">
	<div class="flex flex-row space-x-8 text-black font-bold">
		<h1 class="text-6xl font-medium">
			<img src="/logoes.png" alt="Toas" class="inline-block w-16 h-16" />
			<p>Toas</p>
		</h1>
	</div>
	<div class="text-3xl">
		<h2>
			<span class="text-orange-400 font-bold">SvelteKit 2</span>
			with
			<span class="text-pink-400 font-bold">Vite 5</span>
			web component.
		</h2>
		<br />
		<h2>
			Just
			<span class="text-green-400 font-bold">import</span>
			to use.
		</h2>
		<br />
		<h2>
			<span class="text-blue-400 font-bold">No</span>
			dependencies.
		</h2>
	</div>
	<div class="flex flex-row space-x-8 text-black font-bold">
		<button
			on:click={ToasSuccess}
			class="mt-4 px-4 py-2 bg-green-500 rounded shadow-md hover:shadow-lg shadow-green-500 hover:shadow-green-800"
		>
			Success
		</button>
		<button
			on:click={ToasLoading}
			class="mt-4 px-4 py-2 bg-yellow-500 rounded shadow-md hover:shadow-lg shadow-yellow-500 hover:shadow-yellow-800"
		>
			Loading
		</button>
		<button
			on:click={ToasError}
			class="mt-4 px-4 py-2 bg-red-500 rounded shadow-md hover:shadow-lg shadow-red-500 hover:shadow-red-800"
		>
			Error
		</button>
	</div>
	<Footer />
</div>

<style>
	button {
		transition: transform 0.3s ease;
	}

	button:hover {
		transform: scale(1.1);
	}

	button:active {
		transform: scale(0.9);
	}
</style>
