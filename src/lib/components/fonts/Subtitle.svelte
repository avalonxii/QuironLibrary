<h3>
	<slot />
</h3>

<style lang="scss">
	@use '../../../scss/typography';
	h3 {
		font-size: map-get($map: typography.$font-size, $key: 'subtitle');
	}
</style>
