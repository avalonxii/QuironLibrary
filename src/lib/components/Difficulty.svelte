<script>
	//@ts-check
	/**@type {number}*/
	export let difficulty = 4;
</script>

<div class="difficulty--{difficulty}">
	<span class="number">{difficulty}</span>
	{#if difficulty == 1}
		<span class="tag">Newbie</span>
	{:else if difficulty == 2}
		<span class="tag">Junior</span>
	{:else if difficulty == 3}
		<span class="tag">intermediated</span>
	{:else if difficulty == 4}
		<span class="tag">advanced</span>
	{/if}
</div>

<style lang="scss">
	@use '../../scss/mixin';

	.difficulty {
		&--1 {
			@include mixin.difficulty(#aad742);
		}

		&--2 {
			@include mixin.difficulty(#6abecd);
		}

		&--3 {
			@include mixin.difficulty(#f1b604);
		}

		&--4 {
			@include mixin.difficulty(#f48925);
		}
	}
</style>
