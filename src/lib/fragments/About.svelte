<script>
	import Avatar from '../components/Avatar.svelte';
</script>

<div class="aboutus__bc container">
	<div class="aboutus__container">
		<h2 class="subtitle">About Me</h2>
		<div class="aboutus__info">
			<h3 class="medium">HOLA, MI NOMBRE ES Avalon</h3>

			<div class="aboutus__info-info">
				<Avatar />
				<p>
					Soy un estudiante de ciclo formativo de grado superior y esta página web es mi TFG, que
					nace ante la curiosidad de ver hasta donde llego con el desarrollo y estar presente en las
					distintas etapas de este. El nombre de esta web es QUIRON que según la mitológia griega
					fue un centauro inteligente, sabio y de buen carácter que fue tutor de héroes como Aquiles
					o Áyax.
				</p>
			</div>
		</div>
	</div>
</div>

<style lang="scss">
	@use '../../scss/colors';
	@use '../../scss/mixin';

	.aboutus {
		&__bc {
			margin-bottom: 3rem;
		}

		&__container {
			position: relative;
			border: 1px solid map-get($map: colors.$colors, $key: 'gray');
			border-radius: 5px;
			margin-top: 3.875rem;
			@include mixin.containerPadding($paddingH: 1.4rem);

			.medium {
				margin-bottom: 1.4rem;
			}

			.subtitle {
				background-color: white;
				position: absolute;
				right: 20px;
				top: -25px;
			}
		}

		&__info-info {
			display: flex;
			align-items: center;
			gap: 2rem;
			margin-bottom: 3rem;
		}

		&__questions {
			border-top: 2px solid map-get($map: colors.$colors, $key: 'gray');
		}
	}
</style>
