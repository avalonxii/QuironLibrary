<script>
	import Icon from '@iconify/svelte';
</script>

<div class="button__container">
	<a href="#menu" class="button--top"><Icon icon="material-symbols:arrow-upward-rounded" /></a>
</div>

<style lang="scss">
	@use '../../scss/colors';

	.button {
		&__container {
			position: fixed;
			bottom: 10%;
			right: 4%;
			background-color: map-get($map: colors.$colors, $key: 'primary');
			width: 3.125rem;
			height: 3.125rem;

			border-radius: 100%;
			overflow: hidden;
		}

		&--top {
			width: 100%;
			height: 100%;
			display: flex;
			justify-content: center;
			align-items: center;
			font-size: 2rem;
			color: map-get($map: colors.$colors, $key: 'white');
		}
	}
</style>
