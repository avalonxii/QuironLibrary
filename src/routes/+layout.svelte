<script>
	import Icon from '@iconify/svelte';
	import Avatar from '$lib/components/Avatar.svelte';
	import Link from '$lib/components/Link.svelte';
	import NotificationIcon from '$lib/components/NotificationIcon.svelte';
	import Header from '$lib/components/Header.svelte';
	import Menu from '$lib/components/Menu.svelte';
	import Footer from '$lib/fragments/Footer.svelte';

	let links = [
		{ label: 'Home', href: '/' },
		{ label: 'Challenges', href: 'challenges' },
		{ label: 'Community', href: 'community' },
		{ label: 'Solutions', href: 'solutions' }
	];
</script>

<Header>
	<div class="logo">Quiron</div>
	<Menu>
		{#each links as { label, href }}
			<li><Link {label} {href} /></li>
		{/each}

		<li><NotificationIcon on:click={() => console.log('go to notifications')} /></li>
		<li><Avatar small on:click={() => console.log('go to profile')} /></li>
	</Menu>
</Header>

<div class="contenido">
	<slot />
</div>

<Footer />

<style lang="scss">
	@use '../scss/reset';
	@use '../scss/colors';
	@use '../scss/mixin';

	:global(.contenido) {
		min-height: 100vh;
		padding-top: 4.0625rem;
	}

	:global(.text-ellipsis) {
		@include mixin.text-ellipsis(4);
	}

	:global(.icon) {
		color: map-get($map: colors.$colors, $key: 'black');
		font-size: 2rem;
		padding: 0.3rem;
		cursor: pointer;

		&:hover {
			transform: scale(1.1);
		}
	}
</style>
