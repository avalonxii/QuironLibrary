<script>
	import Icon from '@iconify/svelte';
	//@ts-check
	/** @type {string}*/
	export let label = 'label';

	/** @type {string}*/
	export let name = 'name';

	/** @type {string}*/
	export let type = 'text';

	/** @type {string}*/
	export let value = '';

	/** @type {boolean}*/
	export let required = false;

	/** @type {boolean}*/
	export let error = false;

	let props = { ...$$restProps };

	let seePassw = false;

	//value={props.value ?? ''}
</script>

<div class="input__wrapper">
	<input
		class={`input ${props.class}`}
		type={seePassw ? 'text' : type}
		placeholder="&nbsp;"
		{value}
		{name}
		{required}
	/>

	<label class="label" for="input">{label}</label>

	{#if type == 'password'}
		<button
			type="button"
			class="icon {seePassw ? 'icon--active' : ''}"
			on:click={() => (seePassw = !seePassw)}
		>
			{#if seePassw}
				<Icon icon="mdi:eye" />
			{:else}
				<Icon class="see-pssw" icon="mdi:eye-off" />
			{/if}
		</button>
	{/if}

	<span class="focus-bg" />
	<span class={error ? 'error' : 'normal'}><slot /></span>
</div>

<style lang="scss">
	@use '../../../scss/mixin';
	@use '../../../scss/colors';

	.input__wrapper {
		@include mixin.input();
		min-width: 300px;
		min-height: 100px;
	}

	.error {
		padding: 0.75rem;
		color: map-get($map: colors.$colors, $key: 'error');
	}

	.normal {
		display: none;
	}
</style>
