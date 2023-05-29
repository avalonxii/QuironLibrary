<script>
	import Avatar from '$lib/components/Avatar.svelte';
	import Smalltext from '$lib/components/fonts/Smalltext.svelte';

	export let user;
</script>

<button class="card-user__container" on:click>
	<Avatar small />
	<div class="card-user__info">
		<div class="card-user__name">
			nombre <li class="points">50</li>
		</div>
		<Smalltext>@Usuarios</Smalltext>
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
