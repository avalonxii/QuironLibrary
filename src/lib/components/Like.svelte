<script>
	/** @type {number}*/
	export let likes = 0;
</script>

<label class="like">
	<input type="checkbox" />
	<div class="checkmark">
		<svg viewBox="0 0 256 256">
			<rect fill="none" height="256" width="256" />
			<path
				d="M224.6,51.9a59.5,59.5,0,0,0-43-19.9,60.5,60.5,0,0,0-44,17.6L128,59.1l-7.5-7.4C97.2,28.3,59.2,26.3,35.9,47.4a59.9,59.9,0,0,0-2.3,87l83.1,83.1a15.9,15.9,0,0,0,22.6,0l81-81C243.7,113.2,245.6,75.2,224.6,51.9Z"
				stroke-width="20px"
				stroke="#FFF"
				fill="none"
			/></svg
		>
	</div>
	{likes}
</label>

<style lang="scss">
	@use '../../scss/colors';

	.like {
		transform: scale(0.7);
		position: relative;
		display: block;
		width: 2.5rem;
		cursor: pointer;
		font-size: 20px;
		user-select: none;
		transition: 100ms;
		text-align: center;

		input {
			position: absolute;
			opacity: 0;
			cursor: pointer;
			height: 0;
			width: 0;

			&:checked ~ .checkmark path {
				fill: map-get($map: colors.$colors, $key: 'primary');
				stroke-width: 0;
			}

			&:checked ~ .checkmark {
				animation: like_effect 400ms ease;
			}
		}

		.checkmark {
			top: 0;
			left: 0;
			height: 2em;
			width: 2em;
			transition: 100ms;
			animation: dislike_effect 400ms ease;

			path {
				stroke: map-get($map: colors.$colors, $key: 'black');
			}

			&:hover {
				transform: scale(1.2);
			}
		}
	}

	@keyframes like_effect {
		0% {
			transform: scale(0);
		}

		50% {
			transform: scale(1.2);
		}

		100% {
			transform: scale(1);
		}
	}

	@keyframes dislike_effect {
		0% {
			transform: scale(0);
		}

		50% {
			transform: scale(1.2);
		}

		100% {
			transform: scale(1);
		}
	}
</style>
