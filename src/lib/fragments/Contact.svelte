<script>
	import TextArea from '../components/TextArea.svelte';
	import Button from '../components/Button.svelte';

	// cambiar componente

	/** @type {string}*/
	export let usuario = true;
</script>

<div class="contact">
	{#if usuario}
		<TextArea />
		<Button label="Send" primary />
	{:else}
		<Button label="Log in" primary />
	{/if}
</div>
