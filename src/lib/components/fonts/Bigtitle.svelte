<h1>
	<slot />
</h1>

<style lang="scss">
	@use '../../../scss/typography';
	@use '../../../scss/mixin';

	h1 {
		font-size: map-get($map: typography.$font-size, $key: 'big');
		@include mixin.underlineAnimation();
		margin-bottom: 2rem;
	}
</style>
