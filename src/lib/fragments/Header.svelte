<script>
	import ReturnTop from '../components/ReturnTop.svelte';
	import Menu from './Menu.svelte';
	import ContainerCentred from '../components/ContainerCentred.svelte';
</script>

<div class="header">
	<ContainerCentred class="display">
		<div class="header__logo">QUIRON</div>
		<Menu />
	</ContainerCentred>
</div>

<ReturnTop />

<style lang="scss">
	@use '../../scss/colors';

	.header {
		background-color: map-get($map: colors.$colors, $key: 'bc-white');
		width: 100%;
		position: fixed;
		z-index: 999;
		top: 0;
		box-shadow: rgba(100, 100, 111, 0.2) 0rem 0.4375rem 1.8125rem 0rem;

		&__logo {
			width: fit-content;
			padding: 0.5rem;
			cursor: pointer;
		}
	}
</style>
