<script>
	//@ts-check

	/** @type {string} */
	export let label = 'label';

	/** @type {boolean} */
	export let secondary = false;

	/** @type {boolean} */
	export let code = false;

	/** @type {boolean} */
	export let disabled = false;
</script>

{#if code}
	<button on:click class="code">
		<span>
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
				<path fill="none" d="M0 0h24v24H0z" />
				<path
					fill="currentColor"
					d="M24 12l-5.657 5.657-1.414-1.414L21.172 12l-4.243-4.243 1.414-1.414L24 12zM2.828 12l4.243 4.243-1.414 1.414L0 12l5.657-5.657L7.07 7.757 2.828 12zm6.96 9H7.66l6.552-18h2.128L9.788 21z"
				/>
			</svg>
			Code
		</span>
	</button>
{:else}
	<button on:click class={secondary ? 'secondary' : 'primary'} {disabled}>{label}</button>
{/if}

<style lang="scss">
	@use '../../scss/colors';
	@use '../../scss/mixin';

	.primary {
		@include mixin.button();
	}

	.secondary {
		@include mixin.button(
			$color: map-get($map: colors.$colors, $key: 'secondary'),
			$type: 'secondary'
		);
	}

	.code {
		@include mixin.button($type: 'code');
	}
</style>
