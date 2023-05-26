<script>
	/** @type {string}*/
	export let name;
</script>

<div class="creator">
	<slot />
	{name}
</div>

<style lang="scss">
	@use '../../scss/mixin';
	@use '../../scss/colors';

	.creator {
		@include mixin.containerPadding;
		border-top: 0.125rem solid map-get($map: colors.$colors, $key: 'primary');

		background-color: map-get($map: colors.$colors, $key: 'gray');
		display: flex;
		justify-content: space-between;

		.copy {
			display: flex;
			align-items: center;
			gap: 1rem;
		}
	}
</style>
