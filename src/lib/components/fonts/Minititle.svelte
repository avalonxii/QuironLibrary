<script>
	/** @type {boolean}*/
	export let underlined = false;
</script>

<p class={underlined ? 'underlined' : ''}>
	<slot />
</p>

<style lang="scss">
	@use '../../../scss/typography';
	@use '../../../scss/mixin';

	p {
		position: relative;
		font-weight: bold;
		font-size: map-get($map: typography.$font-size, $key: 'medium');
		margin-bottom: 1rem;
		padding: 0 0.4rem;
	}

	.underlined::before {
		content: '';
		position: absolute;
		left: 24px;
		bottom: -2px;
		width: 150px;
		height: 14px;
		transform: skew(-12deg) translateX(-50%);
		background: rgba(238, 111, 87, 0.5);
		z-index: -1;
	}
</style>
