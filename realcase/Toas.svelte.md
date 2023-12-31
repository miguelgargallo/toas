```svelte
<script>
	import { onMount } from 'svelte';
	let show = false;
	let message = '';
	let type = ''; // 'success', 'loading', 'error'

	// @ts-ignore
	function showToas(msg, msgType) {
		if (!msg) {
			console.error('No message provided for toas');
			return;
		}
		message = msg;
		type = msgType;
		show = true;
		setTimeout(() => {
			show = false;
		}, 3000);
	}

	onMount(() => {
		if (!window) {
			console.error('Window object is not available');
			return;
		}
		// @ts-ignore
		window['showToas'] = showToas;
	});
</script>

{#if show}
	<div class="toas {type}">
		{message}
	</div>
{/if}

<style>
	.toas {
		position: fixed;
		display: flex;
		top: 1%;
		left: 50%;
		transform: translateX(-50%);
		padding: 10px;
		border-radius: 5px;
		background-color: #fff;
		z-index: 9999;
		box-shadow: 0 0 10px #000;
	}

	.toas.success {
		background-color: #4caf50;
		color: #000;
	}

	.toas.loading {
		background-color: #ff9800;
		color: #000;
	}

	.toas.error {
		background-color: #f44336;
		color: #000;
	}
</style>
```