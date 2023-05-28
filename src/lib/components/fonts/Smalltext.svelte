<p><slot /></p>

<style lang="scss">
	@use '../../../scss/typography';
	@use '../../../scss/colors';

	p {
		font-size: map-get($map: typography.$font-size, $key: 'small');
		color: rgb(156, 156, 156);
		margin-bottom: 0.1875rem;
	}
</style>
