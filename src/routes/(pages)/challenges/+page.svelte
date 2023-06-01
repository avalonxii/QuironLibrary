<script>
	import Icon from '@iconify/svelte';
	import ContainerCentred from '$lib/components/ContainerCentred.svelte';
	import Craousel from '$lib/components/carousel/Carousel.svelte';
	import Card from '$lib/components/card/Card.svelte';
	import MetaIcon from '$lib/components/MetaIcon.svelte';
	import Difficulty from '$lib/components/Difficulty.svelte';

	let src = 'https://www.lavanguardia.com/files/og_thumbnail/uploads/2022/07/25/62de6567185fa.jpeg';

	let tags = ['html', 'css', 'js', 'api'];

	//event
	const handlerNavigation = () => {
		console.log('navigate to sun');
	};
</script>

<!-- 
<div class="bc">
	<ContainerCentred>
		<Craousel autoplay="7000">
			<div class="page">
				<Card />
				<Card />
				<Card />
				<Card />
				<Card />
				<Card />
			</div>
			<div class="page">
				<Card />
				<Card />
				<Card />
				<Card />
				<Card />
				<Card />
			</div>
			<div class="page">
				<Card />
				<Card />
				<Card />
				<Card />
			</div>
			<span class="centro" slot="prev-control"><Icon icon="bxs:left-arrow" /></span>
			<span class="centro" slot="next-control"><Icon icon="bxs:right-arrow" /></span>
		</Craousel>
	</ContainerCentred>
</div> -->

<Card on:click={handlerNavigation}>
	<img slot="card__image" {src} alt="imagen ejercicio" />
	<span slot="card__submitted-date">submitetd 5 minutes ago</span>
	<span class="card__title" slot="card__title"> Title de prueba largo ellipsis </span>
	<div slot="card__difficulty">
		<Difficulty />
	</div>
	<div class="card__tags" slot="card__tags">
		{#each tags as tag}
			<span class={`card__tags--${tag}`}>{tag}</span>
		{/each}
	</div>
	<div class="card__options" slot="card__options">
		<MetaIcon>
			<Icon icon="icon-park-outline:like" />
			<span slot="meta-info">10</span>
		</MetaIcon>
	</div>
	Ejemplo dedescripcion del solucion, Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam
	vero, excepturi minima, atque optio rem ipsa, aperiam quasi eum ullam voluptas aliquid quos! Tenetur
	maxime placeat temporibus autem eum? Atque!
</Card>

<style lang="scss">
	@use '../../../scss/mixin';

	.centro {
		display: flex;
		align-items: center;
	}
	.page {
		width: fit-content;
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		gap: 2rem;
	}

	.card__title {
		@include mixin.text-ellipsis(2);
	}

	.card__tags {
		display: flex;
		gap: 0.7rem;
		text-transform: uppercase;
		font-weight: bold;

		&--html {
			color: rgb(133, 195, 215);
		}

		&--css {
			color: rgb(238, 107, 107);
		}

		&--js {
			color: rgb(96, 226, 96);
		}

		&--api {
			color: rgb(31, 185, 177);
		}
	}

	img {
		width: 100%;
		height: 100%;

		&:hover {
			transform: scale(1.1);
			transition: 0.35s;
		}
	}
</style>
