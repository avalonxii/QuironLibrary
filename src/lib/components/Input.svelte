<script>
	import Icon from '@iconify/svelte';
	//@ts-check
	/** @type {string}*/
	export let label = 'label';
	/**
	 *  tipos : password, resto(email, text , date)
	 *  @type {string}*/
	export let type = 'type';

	let seePassw = false;
</script>

<div class="input__wrapper">
	<input class="input" type={seePassw ? 'text' : type} placeholder="&nbsp;" name="input" />

	<label class="label" for="input">{label}</label>

	{#if type == 'password'}
		<button class="icon {seePassw ? 'icon--active' : ''}" on:click={() => (seePassw = !seePassw)}>
			{#if seePassw}
				<Icon icon="mdi:eye" />
			{:else}
				<Icon class="see-pssw" icon="mdi:eye-off" />
			{/if}
		</button>
	{/if}

	<span class="focus-bg" />
	<span class="error-msg">mensaje de error</span>
</div>

<style lang="scss">
	@use '../../scss/mixin';

	.input__wrapper {
		@include mixin.input();
	}
</style>
