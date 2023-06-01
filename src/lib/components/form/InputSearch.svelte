<script>
	/** @type {string}*/
	export let label = 'Search...';

	/** @type {string}*/
	export let name = '';
</script>

<div class="search__container" onsubmit="event.preventDefault();" role="search">
	<label class="search__label" for="search">{label}</label>
	<input class="search__input" type="search" placeholder={label} {name} required />
	<button class="search__button" type="button">Go</button>
</div>

<style lang="scss">
	@use '../../../scss/colors';

	.search {
		&__container {
			position: relative;
			width: 30rem;
			background: map-get($map: colors.$colors, $key: 'gray');
			border-radius: 0.5rem;
		}

		&__input,
		&__button {
			height: 3.4rem;
			border: 0;
			font-size: 1.8rem;
		}

		&__button {
			display: none;
			position: absolute;
			top: 0;
			right: 0;
			width: 6rem;
			font-weight: bold;
			background: map-get($map: colors.$colors, $key: 'success');
			color: map-get($map: colors.$colors, $key: 'white');
			border-radius: 0 0.5rem 0.5rem 0;
		}

		&__input:not(:placeholder-shown) {
			border-radius: 0.5rem 0 0 0.5rem;
			width: calc(100% - 6rem);

			+ button {
				display: block;
			}
		}

		&__label {
			position: absolute;
			clip-path: rect(1px, 1px, 1px, 1px);
			padding: 0;
			border: 0;
			height: 1px;
			width: 1px;
			overflow: hidden;
		}
	}

	input[type='search'] {
		width: 100%;
		background: map-get($map: colors.$colors, $key: 'gray');
		padding: 0 1.6rem;
		border-radius: 0.5rem;
		appearance: none;
		transition: all 0.3s cubic-bezier(0, 0, 0.43, 1.49);
		transition-property: width, border-radius;
		z-index: 1;
		position: relative;
	}
</style>
