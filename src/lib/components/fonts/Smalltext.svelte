<p><slot /></p>

<style lang="scss">
	@use '../../../scss/typography';

	p {
		font-size: map-get($map: typography.$font-size, $key: 'subtitle');
	}
</style>
