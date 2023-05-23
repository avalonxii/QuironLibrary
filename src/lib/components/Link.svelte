<script>
	//@ts-check
	/** @type {string}*/
	export let href = '#';
	/** @type {string}*/
	export let label = 'label';
</script>

<a {href}>{label}</a>

<style lang="scss">
	@use '../../scss/colors';

	a {
		color: map-get($map: colors.$colors, $key: 'primary');
		font-weight: bold;
		text-transform: capitalize;
		text-decoration: none;
	}
</style>
