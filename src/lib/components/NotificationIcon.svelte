<script>
	import Icon from '@iconify/svelte';

	//@ts-check
	/** @type {string[]}*/
	export let notificaciones = [];
</script>

<button class="noti__wrapper" on:click>
	{#if notificaciones.length > 0}
		<Icon class="icon" icon="tabler:bell-ringing-filled" />
		<span />
	{:else}
		<Icon class="icon" icon="tabler:bell-filled" />
	{/if}
</button>

<style lang="scss">
	@use '../../scss/colors';

	.noti__wrapper {
		position: relative;
		width: fit-content;
		background-color: transparent;

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

		.icon {
			color: map-get($map: colors.$colors, $key: 'error');
		}
	}
</style>
