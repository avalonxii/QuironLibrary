<script>
	let props = { ...$$restProps };
</script>

<p style={props.style}>
	<slot />
</p>

<style lang="scss">
	@use '../../../scss/typography';
	p {
		font-size: map-get($map: typography.$font-size, $key: 'paragraph');
	}
</style>
