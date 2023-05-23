<slot />

<style lang="scss">
	@use '../scss/reset';
	@use '../scss/colors';

	:global(.icon) {
		color: map-get($map: colors.$colors, $key: 'black');
		font-size: 2rem;
		padding: 0.3rem;
		cursor: pointer;

		&:hover {
			transform: scale(1.1);
		}
	}
</style>
