<script>
	//@ts-check
	/**@type {string}*/
	export let difficulty = 'intermediated';
</script>

<div class="difficulty--{difficulty}">
	<span class="number">2</span>
	<span class="tag">{difficulty}</span>
</div>

<style lang="scss">
	@use '../../scss/mixin';

	.difficulty {
		&--newbie {
			@include mixin.difficulty(#aad742);
		}

		&--junior {
			@include mixin.difficulty(#6abecd);
		}

		&--intermediated {
			@include mixin.difficulty(#f1b604);
		}

		&--advanced {
			@include mixin.difficulty(#f48925);
		}
	}
</style>
