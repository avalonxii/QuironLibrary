<script>
	/** @type {import('./$types').LayoutData} */
	export let data;
</script>

<div class="contenido">
	<slot />
</div>

<style lang="scss">
	.contenido {
		display: grid;
		align-items: center;
	}
</style>
