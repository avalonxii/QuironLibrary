<script>
	import Button from '$lib/components/Button.svelte';
	import ContainerCentred from '$lib/components/ContainerCentred.svelte';
	import Title from '$lib/components/fonts/Title.svelte';
	import Input from '$lib/components/form/Input.svelte';

	/** @type {import('./$types').PageData} */
	export let data;
</script>

<div class="bc">
	<ContainerCentred>
		<form action="" class="login__container">
			<div class="title"><Title>Log In</Title></div>
			<Input label="Enter your email" type="email" required />
			<Input label="Enter your password" type="password" />
			<Button label="Enviar">enviar</Button>
		</form>
	</ContainerCentred>
</div>

<style lang="scss">
	@use '../../scss/colors';

	.login {
		&__container {
			position: relative;
			border: 0.1875rem solid map-get($map: colors.$colors, $key: 'gray');
			border-radius: 1rem;
			padding: 3.3rem;
			display: grid;
			gap: 1rem;

			.title {
				position: absolute;
				top: -30px;
				left: 30px;
				display: flex;
				background-color: map-get($map: colors.$colors, $key: 'bc-white');
			}
		}
	}
</style>
