<p>
	- <slot />
</p>

<style lang="scss">
	@use '../../../scss/typography';

	p {
		font-weight: bold;
		font-size: map-get($map: typography.$font-size, $key: 'medium');
		margin-bottom: 1rem;
	}
</style>
