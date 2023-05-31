<script lang="ts">
	import Avatar from '../Avatar.svelte';

	export let name: string;

	/* 	import img from '$uploads/9967bc31-430d-417d-99b6-e8245f106754.webp';
	 */

	let uploadedImg: string;

	const handleSelectedImg = (e: Event) => {
		const img = (e.target as HTMLInputElement)?.files?.[0];
		if (!img) return;
		uploadedImg = URL.createObjectURL(img);
	};
</script>

<div class="input__container">
	<button on:click>
		{#if uploadedImg}
			<Avatar src={uploadedImg} />
		{:else}
			<Avatar />
		{/if}
	</button>

	<label>
		UploadPhoto
		<input {name} type="file" accept="image/*" on:change={handleSelectedImg} />
	</label>
</div>

<style lang="scss">
	@use '../../../scss/mixin';

	button {
		background-color: transparent;
		pointer-events: none;
	}

	.input {
		&__container {
			display: flex;
			flex-direction: column;
			align-items: center;
			gap: 1rem;

			input {
				display: none;
				opacity: 0;
				height: 0;
			}

			label {
				@include mixin.button($type: 'secondary');
				width: fit-content;
				font-size: 1rem;
			}
		}
	}
</style>
