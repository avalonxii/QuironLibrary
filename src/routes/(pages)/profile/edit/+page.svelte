<script>
	import Avatar from '$lib/components/Avatar.svelte';
	import Button from '$lib/components/Button.svelte';
	import ContainerCentred from '$lib/components/ContainerCentred.svelte';
	import Minititle from '$lib/components/fonts/Minititle.svelte';
	import Title from '$lib/components/fonts/Title.svelte';
	import Input from '$lib/components/form/Input.svelte';
	import InputPhoto from '$lib/components/form/InputPhoto.svelte';
	import TextArea from '$lib/components/form/TextArea.svelte';

	/** @type {import('./$types').PageData} */
	export let data;
</script>

<ContainerCentred>
	<form action="">
		<div class="edit__container">
			<div class="edit__title">
				<Title>Edit Your Profile</Title>
			</div>
			<div class="edit__inputs--first">
				<InputPhoto />
				<div class="names">
					<Input type="text" label="name" />
					<Input type="text" label="username" />
				</div>
			</div>
			<div class="edit__inputs--second">
				<Input type="email" label="email" />
			</div>
			<div class="edit__inputs--third">
				<Input type="password" label="password" />
				<Input type="password" label="password" />
			</div>
			<div class="edit__aboutme">
				<Minititle>About Me:</Minititle>
				<TextArea />
			</div>
			<Button type="submit" label="Editar !!" />
		</div>
	</form>
</ContainerCentred>

<style lang="scss">
	@use '../../../../scss/colors';

	.edit {
		&__container {
			position: relative;
			border: 0.1875rem solid map-get($map: colors.$colors, $key: 'gray');
			border-radius: 1rem;
			padding: 5rem 5rem 2rem;
			margin-top: 5rem;
		}

		&__title {
			position: absolute;
			top: -29px;
			background-color: map-get($map: colors.$colors, $key: 'bc-white');
			padding: 0 0.5rem;
		}

		&__inputs {
			&--first {
				display: flex;
				justify-content: center;
				align-items: center;
				gap: 3rem;

				.names {
					width: 100%;
				}
			}

			&--second {
				margin-top: 1.5rem;
				padding-top: 1.5rem;
				border-top: 0.1875rem solid rgba(map-get($map: colors.$colors, $key: 'primary'), 0.6);
			}

			&--third {
				display: flex;
				gap: 2rem;
			}
		}
	}
</style>
