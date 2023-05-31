<script>
	import TextArea from '../components/form/TextArea.svelte';
	import Button from '../components/Button.svelte';

	// cambiar componente

	/** @type {string}*/
	export let usuario = true;
</script>

<div class="contact">
	{#if usuario}
		<TextArea />
		<Button type="submit" label="Send" primary />
	{:else}
		<Button type="button" label="Log in" primary />
	{/if}
</div>
