<script>
	import { env } from '$env/dynamic/public';
	import { PUBLIC_LUT_PUB_KEY } from '$env/static/public';
	import { browser, building, dev, version } from '$app/environment';
	import { navigating } from '$app/stores';
	import Header from './Header.svelte';
	import Footer from './Footer.svelte';
	import './styles.css';
	import Episodes from './Episodes.svelte';
	export let data;
	$: ({ all_episodes } = data);
</script>

<Header />

<main>
	<div class="vertical_scroll">
		<slot />
		<Footer />
	</div>
	<aside class="vertical_scroll">
		<Episodes episodes={all_episodes} />
	</aside>
</main>

<style lang="postcss">
	main {
		display: grid;
		grid-template-columns: 300px 1fr;
		gap: 20px;
		height: calc(100vh - var(--header_height));
	}

	aside {
		order: -1;
	}

	.vertical_scroll {
		overflow: scroll;
	}
</style>
