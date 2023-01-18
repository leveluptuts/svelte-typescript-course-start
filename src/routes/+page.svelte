<script>
	import Test from '$lib/Test.svelte';
	import '$db/start';
	export let data;

	$: ({ latest_episode } = data);
</script>

<h2>Latest Episode</h2>
<h3>{latest_episode.title}</h3>

<Test />
