<script lang="ts">
	import { onMount } from 'svelte';
	import { writable, get } from "svelte/store";

	let storedText;

	onMount(() => {
		storedText = writable(localStorage.getItem("text" || ""));
		storedText.subscribe(val => localStorage.setItem("text", val));
})
</script>

<section>
	{@debug storedText}
	{#if storedText}
		<!-- svelte-ignore a11y-autofocus -->
		<article contenteditable="true" bind:innerHTML={$storedText} autofocus/>
	{/if}
</section>

<style>
	article {
		background: #fff;
		text-align: center;
		font-size: 3em;
		padding: 1em;
		width: 80vw;
		margin: 2em auto;
		border-radius: 1em;
	}


</style>
