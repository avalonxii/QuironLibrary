<script>
	import ReturnTop from './ReturnTop.svelte';
</script>

<div class="header">
	<slot />
</div>

<ReturnTop />

<style lang="scss">
	@use '../../scss/colors';
	@use '../../scss/mixin';

	.header {
		position: fixed;
		width: 100%;
		min-height: 4.0625rem;
		max-height: 4.0625rem;
		top: 0;
		z-index: 999;
		background-color: map-get($map: colors.$colors, $key: 'bc-white');
		box-shadow: rgba(100, 100, 111, 0.2) 0rem 0.4375rem 1.8125rem 0rem;
		display: flex;
		align-items: center;
		justify-content: space-between;
		@include mixin.containerPadding();
	}
</style>
