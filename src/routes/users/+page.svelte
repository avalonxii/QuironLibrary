<script>
	import Avatar from '$lib/components/Avatar.svelte';
	import ContainerCentred from '$lib/components/ContainerCentred.svelte';
	import MiniUserCard from '$lib/components/card/MiniUserCard.svelte';
	import Input from '$lib/components/form/Input.svelte';
	import InputSearch from '$lib/components/form/InputSearch.svelte';

	/** @type {import('./$types').PageData} */
	export let data;
</script>

<div class="bc">
	<ContainerCentred>
		<div class="users__search">
			<InputSearch />
		</div>

		<div class="users__container">
			{#each { length: 74 } as _, i}
				<div class="users__cell">
					<MiniUserCard border on:click={() => console.log('user')}>
						<div slot="card__image">
							<Avatar small />
						</div>
						<span slot="card__main-data">nombre</span>
						<span slot="card__extra-data">50</span>
						<span slot="card__sub-data">@User</span>
					</MiniUserCard>
				</div>
			{/each}
		</div>
	</ContainerCentred>
</div>

<style lang="scss">
	.bc {
		min-height: 90vh;
		display: flex;
	}

	.users {
		&__container {
			display: flex;
			flex-wrap: wrap;
			gap: 1.2rem;
		}
		&__search {
			margin-top: 2rem;
			margin-bottom: 3rem;
		}
	}
</style>
