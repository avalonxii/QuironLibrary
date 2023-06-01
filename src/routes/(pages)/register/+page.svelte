<script>
	import ContainerCentred from '$lib/components/ContainerCentred.svelte';
	import Input from '$lib/components/form/Input.svelte';
	import InputPhoto from '$lib/components/form/InputPhoto.svelte';
	import Button from '$lib/components/Button.svelte';
	import Title from '$lib/components/fonts/Title.svelte';
	import Minititle from '$lib/components/fonts/Minititle.svelte';

	/** @type {import('./$types').PageData} */
	export let data;
</script>

<div class="bc">
	<ContainerCentred>
		<form action="" class="register__container">
			<div class="title"><Title>Register</Title></div>
			<div class="register__inputs">
				<Input label="what's ur name?" type="text" name="name">hola</Input>
				<Input label="what's ur usernme?" type="text" name="username">hola</Input>
				<Input label="what's ur email?" type="email" name="email" />
				<Input label="what's ur password?" type="password" name="password" />
				<Input label="repeat password" type="password" />
			</div>

			<div class="register__other">
				<InputPhoto label="repeat password" type="email" name="image" />
				<Button label="Enviar">enviar</Button>
			</div>
		</form>

		<div class="go-login">
			<div class="title"><Minititle>You already have an account ?</Minititle></div>
			<div />
			<Button label="Navigate to Login" on:click={() => console.log('to login')} secondary />
		</div>
	</ContainerCentred>
</div>

<style lang="scss">
	@use '../../../scss/colors';

	.register {
		&__container {
			position: relative;
			border: 0.1875rem solid map-get($map: colors.$colors, $key: 'gray');
			border-radius: 1rem;
			padding: 1.3rem;
			display: grid;
			grid-template-columns: 1fr 1fr;
			gap: 1rem;

			.title {
				position: absolute;
				right: 40px;
				top: -30px;
				background-color: map-get($map: colors.$colors, $key: 'bc-white');
			}
		}

		&__inputs {
			border-right: 2px solid map-get($map: colors.$colors, $key: 'gray');
			padding-right: 1rem;
		}

		&__other {
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			padding: 3rem 0;
		}
	}

	.go-login {
		position: relative;
		border: 0.1875rem solid map-get($map: colors.$colors, $key: 'gray');
		border-radius: 1rem;
		padding: 1.3rem;
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 1rem;
		margin-top: 2rem;
		justify-self: end;

		.title {
			position: absolute;
			top: -12px;
			left: 30px;
			background-color: map-get($map: colors.$colors, $key: 'bc-white');
		}
	}
</style>
