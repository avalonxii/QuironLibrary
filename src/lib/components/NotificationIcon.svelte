<script>
	import Icon from '@iconify/svelte';
	//@ts-check
	/** @type {string[]}*/
	export let notificaciones = [''];
</script>

{#if notificaciones.length > 0}
	<div class="noti__wrapper">
		<Icon class="icon" icon="tabler:bell-ringing-filled" />
		<span />
	</div>
{:else}
	<Icon class="icon" icon="tabler:bell-filled" />
{/if}

<style lang="scss">
	@use '../../scss/colors';

	.noti__wrapper {
		position: relative;
		width: fit-content;

		span {
			border: 0.125rem solid map-get($map: colors.$colors, $key: 'gray');
			background-color: map-get($map: colors.$colors, $key: 'primary');
			position: absolute;
			border-radius: 50%;
			display: flex;
			justify-content: center;
			align-items: center;
			width: 1rem;
			height: 1rem;
			bottom: 0.1875rem;
			right: 0.1875rem;
			transform: scale(0.7);
		}
	}
</style>
