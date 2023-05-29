<script>
	//@ts-check

	/** @type {boolean}*/
	export let error;
</script>

<div class="text-area__wrapper">
	<textarea name="textarea" class="input" cols="30" rows="10" />

	<span class="focus-bg" />
	<span class={error ? 'error' : 'normal'}>mensaje de error</span>
</div>

<style lang="scss">
	@use '../../../scss/mixin';
	@use '../../../scss/colors';

	.error {
		padding: 0.75rem;
		color: map-get($map: colors.$colors, $key: 'error');
	}

	.normal {
		display: none;
	}

	.text-area__wrapper {
		@include mixin.input();
		min-height: 13rem;

		.input {
			height: 10.625rem;
			resize: none;
			padding: 1rem;

			&::-webkit-scrollbar {
				width: 0.4875rem;
			}

			&::-webkit-scrollbar-thumb {
				border-radius: 0.625rem;
				-webkit-box-shadow: inset 0 0 0.375rem
					rgba(map-get($map: colors.$colors, $key: 'primary'), 0.3);
				background-color: map-get($map: colors.$colors, $key: 'primary');
			}

			&:not(:focus) {
				&.input::-webkit-scrollbar-thumb {
					border-radius: 0.625rem;
					-webkit-box-shadow: inset 0 0 0.375rem
						rgba(map-get($map: colors.$colors, $key: 'primary'), 0.3);
					background-color: rgba(map-get($map: colors.$colors, $key: 'black'), 0.5);
				}
			}
		}
	}
</style>
