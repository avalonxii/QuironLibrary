<script>
	import Paragraph from '$lib/components/fonts/Paragraph.svelte';
	import Subtitle from '$lib/components/fonts/Subtitle.svelte';
	import Smalltext from '$lib/components/fonts/Smalltext.svelte';

	/** @type {boolean}*/
	export let solution = false;

	/** @type {number}*/
	export let id = 0;
</script>

<div class="card__container">
	<div class="card__image">
		<slot name="card__image" />
	</div>

	<div class="card__info">
		<div class="card__header">
			{#if solution}<Smalltext><slot name="card__submitted-date" /></Smalltext>{/if}
			<div class="card__title">
				<Subtitle><slot name="card__title" /></Subtitle>
				<slot name="card__difficulty" />
			</div>
			<div class="card__submitted-hashtags">
				<slot name="card__submitted-hashtags" />
			</div>
		</div>

		<div class="card__extra-info">
			<div class="card__tags"><slot name="card__tags" /></div>
			<div class="card__options"><slot name="card__options" /></div>
		</div>
		<div class="meta--info">
			{#if solution}
				<div class="card__user"><slot name="card__user" /></div>
			{/if}
			<div class="card__resume">
				<Paragraph class="text-ellipsis"><slot /></Paragraph>
			</div>
		</div>
	</div>
</div>

<style lang="scss">
	@use '../../../scss/colors';

	$border-radius: 0.65rem;
	$interPadding: 1rem;

	.card {
		&__container {
			border: 0.125rem solid map-get($map: colors.$colors, $key: 'gray');
			border-radius: $border-radius;
			width: 24.375rem;
			overflow: hidden;
		}

		&__image {
			border-top-left-radius: $border-radius;
			border-top-right-radius: $border-radius;
			height: 14.375rem;
			overflow: hidden;

			cursor: pointer;
		}

		&__info {
			padding: 1rem;
		}

		&__title {
			padding-bottom: $interPadding;
			display: flex;
			justify-content: space-between;
		}
		&__submitted-hashtags {
			color: map-get($map: colors.$colors, $key: 'primary');
			margin-bottom: $interPadding;
			font-weight: bold;
		}

		&__tags {
			padding: $interPadding 0;
		}

		&__extra-info {
			display: flex;
			justify-content: space-between;
			align-items: center;
		}

		&__user,
		&__resume {
			padding: $interPadding 0;
			border-top: 2px solid map-get($map: colors.$colors, $key: 'gray');
		}
	}
</style>
