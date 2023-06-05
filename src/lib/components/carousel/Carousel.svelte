<script>
	import { createEventDispatcher, onMount } from 'svelte';
	import Siema from 'siema';

	export let perPage = 1;
	export let loop = true;
	export let autoplay = 0;
	export let duration = 500;
	export let easing = 'ease-out';
	export let startIndex = 0;
	export let draggable = false;
	export let multipleDrag = false;
	export let dots = false;
	export let controls = true;
	export let threshold = 20;
	export let rtl = false;
	let currentIndex = startIndex;

	let siema;
	let controller;
	let timer;
	const dispatch = createEventDispatcher();

	$: pips = controller ? controller.innerElements : [];
	$: currentPerPage = controller ? controller.perPage : perPage;
	$: totalDots = controller ? Math.ceil(controller.innerElements.length / currentPerPage) : [];

	onMount(() => {
		controller = new Siema({
			selector: siema,
			perPage: typeof perPage === 'object' ? perPage : Number(perPage),
			loop,
			duration,
			easing,
			startIndex,
			draggable,
			multipleDrag,
			threshold,
			rtl,
			onChange: handleChange
		});

		if (autoplay) {
			timer = setInterval(right, autoplay);
		}
		return () => {
			autoplay && clearInterval(timer);
			controller.destroy();
		};
	});

	export function isDotActive(currentIndex, dotIndex) {
		if (currentIndex < 0) currentIndex = pips.length + currentIndex;
		return (
			currentIndex >= dotIndex * currentPerPage &&
			currentIndex < dotIndex * currentPerPage + currentPerPage
		);
	}

	export function left() {
		controller.prev();
	}

	export function right() {
		controller.next();
	}

	export function go(index) {
		controller.goTo(index);
	}

	export function pause() {
		clearInterval(timer);
	}

	export function resume() {
		if (autoplay) {
			timer = setInterval(right, autoplay);
		}
	}

	function handleChange(event) {
		currentIndex = controller.currentSlide;
		dispatch('change', {
			currentSlide: controller.currentSlide,
			slideCount: controller.innerElements.length
		});
	}

	function resetInterval(node, condition) {
		function handleReset(event) {
			pause();
			resume();
		}

		if (condition) {
			node.addEventListener('click', handleReset);
		}

		return {
			destroy() {
				node.removeEventListener('click', handleReset);
			}
		};
	}
</script>

<div class="carousel__container">
	<div class="carousel__photo" bind:this={siema}>
		<slot />
	</div>

	{#if controls}
		<div class="carousel__buttons">
			<button class="prev" on:click={left} use:resetInterval={autoplay}>
				<slot name="prev-control" />
			</button>

			<button class="next" on:click={right} use:resetInterval={autoplay}>
				<slot name="next-control" />
			</button>
		</div>
	{/if}

	{#if dots}
		<div class="pagination__container">
			{#each { length: totalDots } as _, i}
				<button
					on:click={() => go(i * currentPerPage)}
					class={isDotActive(currentIndex, i) ? 'active' : ''}
				/>
			{/each}
		</div>
	{/if}
</div>

<style lang="scss">
	@use '../../../scss/colors';

	.carousel {
		&__container {
			position: relative;
			border: 3px solid map-get($map: colors.$colors, $key: 'gray');
			border-radius: 1rem;
			padding: 2rem 1rem;

			display: flex;
			justify-content: center;
		}

		&_photo {
			min-width: 100%;
		}

		&__buttons {
			position: absolute;
			left: 0;
			top: 50%;
			width: 100%;
			display: flex;
			justify-content: space-between;
			align-items: center;

			.prev,
			.next {
				padding: 0.6rem;
				font-size: 1.2rem;
				border-radius: 0.3125rem;
				cursor: pointer;
				border: 2px solid map-get($map: colors.$colors, $key: 'gray');
				color: map-get($map: colors.$colors, $key: 'primary');

				display: flex;
				align-items: center;
				justify-content: center;

				&:hover {
					transform: scale(1.1);
					transition: 0.25s;
				}

				&:active {
					transform: scale(0.9);
					transition: 0.25s;
				}
			}
		}
	}
</style>
