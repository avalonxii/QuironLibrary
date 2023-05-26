<h2>
	<slot />
</h2>

<style lang="scss">
	@use '../../../scss/typography';
	@use '../../../scss/mixin';

	h2 {
		font-size: map-get($map: typography.$font-size, $key: 'title');
		@include mixin.underlineAnimation();
		margin-bottom: 2rem;
	}
</style>
