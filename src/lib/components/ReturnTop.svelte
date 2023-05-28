<script>
	import Button from '$lib/components/Button.svelte';
	import Icon from '@iconify/svelte';

	function goTopPage() {
		window.scrollTo({
			top: 0,
			behavior: 'smooth'
		});
	}
</script>

<button class="button__container" on:click={goTopPage}>
	<Icon class="button--top" icon="material-symbols:arrow-upward-rounded" />
</button>

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

			display: flex;
			justify-content: center;
			align-items: center;
			font-size: 2rem;
			color: map-get($map: colors.$colors, $key: 'white');
			cursor: pointer;
		}
	}
</style>
