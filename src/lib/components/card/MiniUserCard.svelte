<script>
	import Smalltext from '$lib/components/fonts/Smalltext.svelte';

	/** @type {boolean}*/
	export let border = false;
</script>

<button class={`card-user__container ${border ? 'border' : ''}`} on:click>
	<div class="card__image">
		<slot name="card__image" />
	</div>
	<div class="card-user__info">
		<div class="card-user__name">
			<slot name="card__main-data" />
			<li class="points"><slot name="card__extra-data" /></li>
		</div>
		<Smalltext><slot name="card__sub-data" /></Smalltext>
	</div>
</button>

<style lang="scss">
	@use '../../../scss/colors';
	@use '../../../scss/typography';

	button {
		background-color: transparent;
		text-align: start;
		font-size: 1rem;
	}

	.border {
		border: 0.3125rem solid map-get($map: colors.$colors, $key: 'gray') !important;
		border-radius: 0.625rem;
		padding: 0.5rem;
	}

	.card-user {
		&__container {
			width: 100%;
			display: flex;
			align-items: center;
			gap: 3rem;
			cursor: pointer;

			&:hover {
				background-color: rgb(250, 250, 250);
			}
		}

		&__info {
			display: grid;
			gap: 0.5rem;
		}

		&__name {
			display: flex;
			gap: 1rem;
			font-weight: bold;

			cursor: pointer;

			.points {
				color: map-get($map: colors.$colors, $key: 'primary');
			}
		}
	}
</style>
