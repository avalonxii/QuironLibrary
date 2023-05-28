<script>
	import Avatar from '$lib/components/Avatar.svelte';
	import Smalltext from '$lib/components/fonts/Smalltext.svelte';

	export let user;
</script>

<div class="card-user__container">
	<Avatar small />
	<div class="card-user__info">
		<div class="card-user__name">
			nombre <li class="points">50</li>
		</div>
		<Smalltext>@Usuarios</Smalltext>
	</div>
</div>

<style lang="scss">
	@use '../../../scss/colors';
	@use '../../../scss/typography';

	.card-user {
		&__container {
			display: flex;
			align-items: center;
			gap: 3rem;
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
