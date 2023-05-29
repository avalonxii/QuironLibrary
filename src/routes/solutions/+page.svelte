<script>
	import Icon from '@iconify/svelte';
	import ContainerCentred from '$lib/components/ContainerCentred.svelte';
	import Card from '$lib/components/card/Card.svelte';
	import MetaIcon from '$lib/components/MetaIcon.svelte';
	import MiniUserCard from '$lib/components/card/MiniUserCard.svelte';

	let src = 'https://www.lavanguardia.com/files/og_thumbnail/uploads/2022/07/25/62de6567185fa.jpeg';

	/** @type {import('./$types').PageData} */
	export let data;

	let tags = ['html', 'css', 'js', 'api'];

	//events
	const handlerNavigation = () => {
		console.log('navigate to sun');
	};
</script>

<div class="bc">
	<ContainerCentred>
		<div class="solution__cards">
			<Card on:click={handlerNavigation} solution>
				<img slot="card__image" {src} alt="imagen ejercicio" />
				<span slot="card__submitted-date">submitetd 5 minutes ago</span>
				<span slot="card__title">Title</span>
				<div slot="card__submitted-hashtags">#hola</div>
				<div class="card__tags" slot="card__tags">
					{#each tags as tag}
						<span class={`card__tags--${tag}`}>{tag}</span>
					{/each}
				</div>
				<div class="card__options" slot="card__options">
					<MetaIcon>
						<Icon icon="ci:chat" />
						<span slot="meta-info">10</span>
					</MetaIcon>
					<MetaIcon>
						<Icon icon="icon-park-outline:like" />
						<span slot="meta-info">10</span>
					</MetaIcon>
					<MetaIcon>
						<Icon icon="fluent:save-copy-20-regular" />
						<span slot="meta-info">10</span>
					</MetaIcon>
				</div>

				<div slot="card__user">
					<MiniUserCard on:click={() => console.log('user')} />
				</div>

				Ejemplo dedescripcion del solucion, Lorem ipsum dolor sit amet consectetur adipisicing elit.
				Quisquam vero, excepturi minima, atque optio rem ipsa, aperiam quasi eum ullam voluptas
				aliquid quos! Tenetur maxime placeat temporibus autem eum? Atque!
			</Card>
		</div>
	</ContainerCentred>
</div>

<style lang="scss">
	.solution {
		&__cards {
			display: flex;
			flex-wrap: wrap;
			justify-content: center;
			column-gap: 0.3125rem;

			img {
				width: 100%;
				height: 100%;

				&:hover {
					transform: scale(1.1);
					transition: 0.35s;
				}
			}
		}
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

	.card__options {
		display: flex;
		gap: 1rem;
	}
</style>
