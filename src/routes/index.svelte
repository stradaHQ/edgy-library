<script>
	import { supabase } from '$lib/db';
	async function getData() {
		const { data, error } = await supabase.from('books').select();
		if (error) throw new Error(error.message);

		return data;
	}
</script>

<svelte:head>
	<title>edgy library</title>
</svelte:head>

<section>
	<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
	{#await getData()}
		<p>Fetching data...</p>
	{:then data}
		{#each data as game}
			<li>{game.title}</li>
		{/each}
	{:catch error}
		<p>Something went wrong while fetching the data:</p>
		<pre>{error}</pre>
	{/await}
</section>
