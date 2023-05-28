<div class="meta__container">
	<div class="meta--icon">
		<slot />
	</div>
	<div class="meta--info">
		<slot name="meta-info" />
	</div>
</div>

<style lang="scss">
	@use '../../scss/colors';

	.meta {
		&__container {
			display: flex;
			flex-direction: column;
			align-items: center;
			font-size: 1.4rem;

			color: map-get($map: colors.$colors, $key: 'black');
		}

		&--icon {
			cursor: pointer;

			&:hover {
				transform: scale(1.1);
			}
			&:active {
				transform: scale(0.9);
			}
		}

		&--info {
			font-size: 0.7rem;
			user-select: none;
		}
	}
</style>
