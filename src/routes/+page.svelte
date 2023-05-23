<script>
	import '../scss/_typography.scss';

	//@ts-check
	import Button from '$lib/components/Button.svelte';
	import Avatar from '$lib/components/Avatar.svelte';
	import Checkbox from '$lib/components/Checkbox.svelte';
	import Difficulty from '$lib/components/Difficulty.svelte';
	import Input from '$lib/components/Input.svelte';
	import Like from '$lib/components/Like.svelte';
	import Link from '$lib/components/Link.svelte';
	import MenuIcon from '$lib/components/MenuIcon.svelte';
	import NotificationIcon from '$lib/components/NotificationIcon.svelte';
	import ReturnTop from '$lib/components/ReturnTop.svelte';
	import Tag from '$lib/components/Tag.svelte';
	import TextArea from '$lib/components/TextArea.svelte';
	import Completed from '$lib/components/Completed.svelte';
</script>

<Button label={'Button'} primary />
<Button label={'Button'} secondary />
<Button code />

<Avatar small />
<Avatar editable />

<Checkbox />

<Difficulty difficulty={'newbie'} />
<Difficulty difficulty={'junior'} />
<Difficulty difficulty={'intermediated'} />
<Difficulty difficulty={'advanced'} />

<Input type="email" />
<Input type="password" />
<Input type="number" />
<Input type="date" />

<TextArea />

<Like />

<Link label="enlace a" />

<MenuIcon />

<NotificationIcon />

<ReturnTop />

<Tag label="html" />

<Completed />

<h1>Welcome to your library project</h1>
<p>Create your package using @sveltejs/package and preview/showcase your work with SvelteKit</p>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<span> hola </span>

<style lang="scss">
</style>
