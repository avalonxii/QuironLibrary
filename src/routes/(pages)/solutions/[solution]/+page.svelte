<script>
	import Button from '$lib/components/Button.svelte';
	import ContainerCentred from '$lib/components/ContainerCentred.svelte';
	import Difficulty from '$lib/components/Difficulty.svelte';
	import Link from '$lib/components/Link.svelte';
	import Carousel from '$lib/components/carousel/Carousel.svelte';
	import Paragraph from '$lib/components/fonts/Paragraph.svelte';
	import Smalltext from '$lib/components/fonts/Smalltext.svelte';
	import Subtitle from '$lib/components/fonts/Subtitle.svelte';
	import Title from '$lib/components/fonts/Title.svelte';
	import Icon from '@iconify/svelte';

	let src = 'https://www.lavanguardia.com/files/og_thumbnail/uploads/2022/07/25/62de6567185fa.jpeg';
</script>

<ContainerCentred>
	<div class="single__container">
		<div class="single__photos">
			<Carousel autoplay={7000}>
				<div>
					<img src="https://pbs.twimg.com/media/FWXeXlmX0AUq2vt.jpg" alt="" />
				</div>
				<div>
					<img src="https://i.blogs.es/1b4f07/maxwell/840_560.jpeg" alt="" />
				</div>
				<div>
					<img
						src="https://img.wattpad.com/804c8738be736f9967303107b2e70ae6938dfd18/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f776174747061642d6d656469612d736572766963652f53746f7279496d6167652f4b336e744647353044724b4c56513d3d2d3133352e313537316565386535366237353137303839363736353935303134322e6a7067?s=fit&w=720&h=720"
						alt=""
					/>
				</div>
				<span class="centro" slot="prev-control"><Icon icon="bxs:left-arrow" /></span>
				<span class="centro" slot="next-control"><Icon icon="bxs:right-arrow" /></span>
			</Carousel>
		</div>

		<div class="single__info">
			<div class="single__other">
				<div class="tags">Html CSS JS JAVA API</div>
				<Difficulty />
			</div>
			<div class="single__title">
				<Subtitle>title largo beb hola que tal como estas</Subtitle>
			</div>
			<div class="single__hastags">#hola #sccss #Api #Verdecito</div>
			<div class="single__description">
				<Paragraph>
					Lorem ipsum dolor sit amet, consectetur adipisicing elit. Incidunt, architecto corrupti
					placeat facere facilis repellendus cum. Iusto reiciendis earum ad odio dolor, dicta est,
					libero, autem voluptas asperiores labore amet.
				</Paragraph>
			</div>
			<!-- <div class="single__buttons">
				<Smalltext>To be able to perform the challenges you have to:</Smalltext>
				<Button label="Log in" secondary />

				<div><Button label="Start Challenge" /></div>
			</div> -->

			<Smalltext>
				puedes encontrar el codigo en <Link href="" label="gitHub" /> creado por <Link
					href=""
					label="creador"
				/>
			</Smalltext>
		</div>
	</div>
</ContainerCentred>

<style lang="scss">
	.single {
		&__container {
			border: 3px solid grey;
			border-radius: 0.7rem;
			display: flex;
			flex-direction: column;
			gap: 1rem;
			padding: 1.3rem;
		}

		&__photos {
			order: 2;

			div {
				min-width: 100%;
				height: 50rem;
				display: flex;
				justify-content: space-around;
			}

			span {
				display: flex;
				justify-content: center;
				align-items: center;
			}
		}

		&__info {
			min-width: 50%;
			order: 1;
			display: flex;
			flex-direction: column;
			justify-content: center;
		}

		&__other {
			display: flex;
			justify-content: space-between;
			margin-bottom: 2rem;
		}

		&__title {
			margin-bottom: 0.625rem;
			overflow-wrap: break-word;
		}

		&__hastags {
			margin-bottom: 1.4rem;
		}

		&__description {
			margin-bottom: 2rem;
		}
	}
</style>
