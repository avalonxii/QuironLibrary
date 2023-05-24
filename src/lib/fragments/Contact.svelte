<script>
	import TextArea from '../components/TextArea.svelte';
	import Button from '../components/Button.svelte';
	let usuario = ' ';
</script>

<div class="contact">
	{#if usuario}
		<TextArea />
		<Button text="Send" primary />
	{:else}
		<Button text="Log in" primary />
	{/if}
</div>
