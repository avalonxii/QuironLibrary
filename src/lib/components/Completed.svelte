<script>
	import Icon from '@iconify/svelte';
</script>

<div class="complete__wrapper">
	<Icon class="complete__icon" icon="mdi:tick-circle-outline" />
	<p class="complete__text">Ya has completado este reto</p>
</div>

<style lang="scss">
	@use '../../scss/colors';

	.complete {
		&__wrapper {
			display: flex;
			align-items: center;
			justify-content: center;
			gap: 1rem;
			color: map-get($map: colors.$colors, $key: 'white');
			user-select: none;
		}
	}
</style>
