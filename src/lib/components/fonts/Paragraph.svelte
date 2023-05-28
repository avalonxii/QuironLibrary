<script>
	let props = { ...$$restProps };
</script>

<p style={props.style} class={props.class}>
	<slot />
</p>

<style lang="scss">
	@use '../../../scss/typography';

	p {
		font-size: map-get($map: typography.$font-size, $key: 'paragraph');
		line-height: 20px;
	}
</style>
