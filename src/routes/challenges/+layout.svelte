<script>
	import Button from '$lib/components/Button.svelte';
	import ContainerCentred from '$lib/components/ContainerCentred.svelte';
	import Title from '$lib/components/fonts/Title.svelte';

	/** @type {import('./$types').LayoutData} */
	export let data;
</script>

<ContainerCentred>
	<div class="challange-container">
		<Title>Challenges</Title>
		<div class="filtros">
			<Button label={"filtro"} />
		</div>
	</div>
</ContainerCentred>
<slot />

<style>
	.challange-container {
		display: flex;
		justify-content: space-between;
	}
</style>
