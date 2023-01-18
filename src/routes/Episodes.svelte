<script>
	import { page } from '$app/stores';
	export let episodes;
</script>

<ul>
	{#each episodes as episode}
		<li class:active={String(episode.number) === $page.params.num}>
			<a href={`/show/${episode.number}`}>Episode {episode.number}<br /> {episode.title}</a>
		</li>
	{/each}
</ul>

<style>
	ul {
		padding: 0;
		list-style: none;
		margin: 0;
	}
	li {
		border-right: solid 1px var(--grey);
		border-bottom: solid 1px var(--grey);
		background: var(--lt_grey);
		padding: 10px;
	}
	li.active {
		background: var(--white);
		border-right: none;
	}
	a {
		display: block;
		text-decoration: none;
		color: var(--black);
		font-weight: 900;
		line-height: 1.5;
	}
</style>
