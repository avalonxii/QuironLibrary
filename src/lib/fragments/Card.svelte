<script>
	import Completed from '../components/Completed.svelte';
	import Difficulty from '../components/Difficulty.svelte';
	import Like from '../components/Like.svelte';

	//@ts-check
	/** @type {string}*/
	export let src = 'https://www.disane.es/wp-content/uploads/husky.jpg';

	/** @type {string}*/
	export let title = 'Titulo de Prueba';

	/** @type {string}*/
	export let description =
		'Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam libero odit quia fugiat quod veniam. Voluptatum, nam sequi quasi fugiat animi provident dolore praesentium nulla quibusdam, itaque quae exercitationem eius!';

	/** @type {string}*/
	export let difficulty = 'advanced';

	/** @type {string[]}*/
	export let tags = ['html', 'css', 'js', 'api'];

	/** @type {boolean}*/
	export let completed = true;
</script>

<div class="card">
	<div class="card__foto">
		<img {src} alt="" />
		{#if completed}
			<span> <Completed /> </span>
		{/if}
	</div>

	<div class="card__info">
		<div class="card__info--top">
			<h3 class="card__title">{title}</h3>
			<Like />
		</div>
		<div class="card__extra-info">
			<div class="chg__tags">
				{#each tags as tag}
					<span class={tag}>{tag}</span>
				{/each}
			</div>
			<div class="chg__level"><Difficulty {difficulty} /></div>
		</div>
		<div class="card__description">
			<p>{description}</p>
		</div>
	</div>
</div>

<style lang="scss">
	@use '../../scss/mixin';

	.card {
		@include mixin.card();
	}
</style>
