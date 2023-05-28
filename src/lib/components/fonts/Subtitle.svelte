<script>
	let props = { ...$$restProps };
</script>

<h3 class={props.class} style={props.style}>
	<slot />
</h3>

<style lang="scss">
	@use '../../../scss/typography';
	h3 {
		width: fit-content;
		font-size: map-get($map: typography.$font-size, $key: 'subtitle');

		&:hover {
			text-decoration: underline;
			cursor: pointer;
		}
	}
</style>
