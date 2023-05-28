<script>
	import Button from '$lib/components/Button.svelte';
	import ContainerCentred from '$lib/components/ContainerCentred.svelte';
	import Title from '$lib/components/fonts/Title.svelte';

	/** @type {import('./$types').LayoutData} */
	export let data;
</script>

<ContainerCentred>
	<div class="solution-container">
		<Title>Solutions</Title>
		<div class="filtros">
			<Button label={'filtro'} />
		</div>
	</div>
</ContainerCentred>
<slot />

<style>
	.solution-container {
		display: flex;
		justify-content: space-between;
	}
</style>
