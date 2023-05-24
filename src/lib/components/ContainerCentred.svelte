<script>
	let props = { ...$$restProps };
</script>

<div class={`${props.class} container`}>
	<slot />
</div>

<style>
	.container {
		width: 100%;
		padding: 0.8rem 14%;
	}

	.display {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
</style>
