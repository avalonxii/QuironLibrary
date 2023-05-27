<script>
	import Icon from '@iconify/svelte';
	import ContainerCentred from '$lib/components/ContainerCentred.svelte';
	import Craousel from '$lib/components/carousel/Craousel.svelte';
	import Card from '$lib/fragments/Card.svelte';
</script>

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
</div>

<style lang="scss">
	.page {
		width: fit-content;
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
		gap: 2rem;
	}
</style>
