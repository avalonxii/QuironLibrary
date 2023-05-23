<script>
	import Icon from '@iconify/svelte';
	//@ts-check
	/** @type {string} */
	export let src = 'http://i.pravatar.cc/500?img=7';

	/** @type {boolean} */
	export let editable = false;

	/** @type {boolean} */
	export let small = false;
</script>

<div class="avatar-component__photo" style="--size: {small ? '2.3rem' : '10.625rem'}">
	{#if editable}
		<div class="avatar-component__edit">
			<input type="file" name="image" accept="image/*" />
			<label for="image"><Icon icon="mdi:pencil" /></label>
		</div>
	{/if}

	<img {src} alt="foto de perfil usuario" />
</div>

<style lang="scss">
	.avatar-component {
		&__photo {
			min-width: var(--size);
			width: var(--size);
			position: relative;
			border-radius: 100%;
			border: 0.0625rem solid #f8f8f8;
			box-shadow: 0rem 0.125rem 0.25rem 0rem rgba(0, 0, 0, 0.1);
			user-select: none;

			> img {
				width: 100%;
				height: 100%;
				border-radius: 100%;
				background-size: cover;
				background-repeat: no-repeat;
				background-position: center;
			}
		}

		&__edit {
			position: absolute;
			right: 0;
			z-index: 10;

			input {
				display: none;
			}

			label {
				width: 2.125rem;
				height: 2.125rem;

				display: flex;
				justify-content: center;
				align-items: center;

				border-radius: 100%;
				background: #ffffff;
				border: 0.0625rem solid transparent;
				box-shadow: 0rem 0.125rem 0.25rem 0rem rgba(0, 0, 0, 0.12);
				font-weight: normal;

				cursor: pointer;
				transition: all 0.2s ease-in-out;

				&:hover {
					background: #f1f1f1;
					border-color: #d6d6d6;
				}
			}
		}
	}
</style>
