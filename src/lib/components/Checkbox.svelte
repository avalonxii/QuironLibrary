<script>
	//@ts-check
	/** @type {string}*/
	export let label = 'label';
</script>

<label class="checkbox__wrapper">
	<input class="checkbox" type="checkbox" />
	{label}</label
>

<style lang="scss">
	@use '../../scss/colors';

	.checkbox__wrapper {
		display: flex;
		align-items: center;
		font-size: 1rem;
		user-select: none;
		cursor: pointer;
	}

	.checkbox {
		position: relative;
		width: 1.4375rem;
		height: 1.375rem;
		display: inline-block;
		margin-right: 0.625rem;

		appearance: none;
		border: 0.1875rem solid map-get($map: colors.$colors, $key: 'primary');
		border-radius: 0.3125rem;
		background-color: transparent;
		cursor: pointer;
	}

	.checkbox:before {
		content: '';
		background-color: map-get($map: colors.$colors, $key: 'primary');
		display: block;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%) scale(0);
		width: 0.875rem;
		height: 0.875rem;
		border-radius: 0.1875rem;
		transition: all 0.3s ease-in-out;
	}

	.checkbox:checked:before {
		transform: translate(-50%, -50%) scale(1);
	}
</style>
