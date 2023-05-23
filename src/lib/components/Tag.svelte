<script>
	import Icon from '@iconify/svelte';
	//@ts-check
	/** @type {string}*/
	export let label = 'label';

	/** @type {boolean}*/
	export let filter = false;
</script>

<div class="tag__wrapper">
	<p>{label}</p>

	{#if filter}
		<Icon icon="ph:x-bold" class="icon-tag" />
	{/if}
</div>

<style lang="scss">
	@use '../../scss/colors';

	.tag__wrapper {
		background-color: map-get($map: colors.$colors, $key: 'gray');
		width: fit-content;
		display: flex;
		align-items: center;
		gap: 1rem;

		padding: 0.4rem 0.5rem;
		border-radius: 5px;

		p {
			font-size: 12px;
			font-weight: bold;
			user-select: none;
			text-transform: uppercase;
		}

		.icon-tag {
			border-radius: 50%;
			display: flex;
			justify-content: center;
			align-items: center;
			cursor: pointer;
		}

		&:hover {
			background-color: rgba(map-get($map: colors.$colors, $key: 'primary'), 0.5);
		}
	}
</style>
