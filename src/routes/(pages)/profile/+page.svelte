<script>
	import Avatar from '$lib/components/Avatar.svelte';
	import ContainerCentred from '$lib/components/ContainerCentred.svelte';
	import MetaIcon from '$lib/components/MetaIcon.svelte';
	import Minititle from '$lib/components/fonts/Minititle.svelte';
	import Paragraph from '$lib/components/fonts/Paragraph.svelte';
	import Smalltext from '$lib/components/fonts/Smalltext.svelte';
	import Subtitle from '$lib/components/fonts/Subtitle.svelte';
	import Title from '$lib/components/fonts/Title.svelte';
	import Card from '$lib/components/card/Card.svelte';
	import Icon from '@iconify/svelte';

	/** @type {import('./$types').PageData} */
	export let data;

	let src = 'https://www.lavanguardia.com/files/og_thumbnail/uploads/2022/07/25/62de6567185fa.jpeg';
</script>

<ContainerCentred>
	<Title>Profile</Title>
</ContainerCentred>
<div class="bc">
	<ContainerCentred>
		<div class="profile__user">
			<div class="profile__info">
				<Avatar />
				<div class="profile__data">
					<Subtitle>Juan</Subtitle>
					<Smalltext>@juan</Smalltext>
					<div class="points">60 points</div>
					<a href="/"><Icon class="icon" icon="fluent-mdl2:git-hub-logo" /></a>
				</div>
			</div>
			<Paragraph
				>Lorem ipsum dolor sit amet consectetur adipisicing elit. Et expedita, quam sit cumque
				cupiditate doloribus totam molestias sunt quibusdam maxime quisquam reprehenderit possimus
				facere reiciendis non nulla ut minus suscipit?
			</Paragraph>
		</div>
	</ContainerCentred>
</div>

<ContainerCentred>
	<div class="profile__solutions">
		<div class="title"><Minititle underlined>last solutions</Minititle></div>

		<div class="solution__cards">
			<Card solution>
				<img slot="card__image" {src} alt="imagen ejercicio" />
				<span slot="card__submitted-date">submitetd 5 minutes ago</span>
				<span slot="card__title">Title</span>
				<div slot="card__submitted-hashtags">
					<span>#hola</span>
					<span>#hola</span>
					<span>#hola</span>
					<span>#hola</span>
					<span>#hola </span>
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

				Ejemplo dedescripcion del solucion, Lorem ipsum dolor sit amet consectetur adipisicing elit.
				Quisquam vero, excepturi minima, atque optio rem ipsa, aperiam quasi eum ullam voluptas
				aliquid quos! Tenetur maxime placeat temporibus autem eum? Atque!
			</Card>
		</div>
	</div>
</ContainerCentred>

<style lang="scss">
	@use '../../../scss/colors';

	.bc {
		background-color: map-get($map: colors.$colors, $key: 'white');
	}

	.profile {
		&__user {
			min-height: 200px;
			padding-top: 1.5rem;
			padding-bottom: 1.5rem;

			display: flex;
			justify-content: space-between;
			align-items: start;
			gap: 20%;
		}

		&__info {
			width: 100%;
			height: 100%;
			display: flex;
			align-items: center;
			gap: 2.5rem;
		}

		&__data {
			display: grid;
			gap: 0.5rem;

			.points {
				font-size: 2rem;
				font-weight: bold;
				color: map-get($map: colors.$colors, $key: 'primary');
			}
		}

		&__solutions {
			margin-bottom: 2rem;
			margin-top: 4.5rem;
			.title {
				height: fit-content;
				display: flex;
				justify-content: center;
			}
		}
	}

	.solution {
		&__cards {
			display: flex;
			flex-wrap: wrap;
			justify-content: start;
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

	.card__options {
		display: flex;
		gap: 1rem;
	}
</style>
