<script>
	import Avatar from '../components/Avatar.svelte';
	import Link from '../components/Link.svelte';
	import NotificationIcon from '../components/NotificationIcon.svelte';

	//@ts-check
	/** @type {{lable:string, href:string}[]} */
	const links = [
		{ lable: 'lable', href: '#' },
		{ lable: 'lable2', href: '#2' }
	];
</script>

<ul class="menu">
	{#each links as link}
		<li><Link label={link.lable} href="/{link.href}" /></li>
	{/each}

	<li><NotificationIcon /></li>
	<li><Avatar small /></li>
</ul>

<style lang="scss">
	.menu {
		display: flex;
		width: fit-content;
		justify-content: end;
		align-items: center;
		gap: 1.3rem;
		list-style: none;
	}
</style>
