<script lang="ts">
	import { writable, get } from "svelte/store";

	const storedLinks = writable(
		JSON.parse(
			localStorage.getItem("links" || "[]")
		)
	);
	storedLinks.subscribe(value => {
		localStorage.setItem("links", JSON.stringify(value));
	});
</script>

<section>
	{#if Array.isArray(get(storedLinks))}
		{#each get(storedLinks) as link}
			<article>
				<a href="{link.url}"><img src="{link.img}" /></a>
			</article>
		{/each}
	{/if}
</section>

<style>
	section {
		display: flex;
		flex-direction: row;
	}
	article {
		text-align: center;
		padding: 1em;
		max-width: 5em;
		margin: 0 auto;
	}
	a {
		display: block;
		width: 100%;
		height: 100%;
		aspect-ratio: 1 / 1;
		background:	linear-gradient(217deg, rgba(200,0,0,.8), rgba(200,0,0,0) 70.71%),
								linear-gradient(127deg, rgba(0,200,0,.8), rgba(0,200,0,0) 70.71%),
								linear-gradient(336deg, rgba(0,0,200,.8), rgba(0,0,200,0) 70.71%);
		padding: 2em;
		border-radius: 1em;
	}
	img {
		max-width: 100%;
		max-height: 100%;
	}

</style>
