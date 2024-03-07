<script lang="ts">
	import type { MouseEventHandler } from 'svelte/elements';

	// export let onClose: MouseEventHandler<HTMLButtonElement>;
	export let src: string | null;
	export let alt: string | null;
	let modalOpen = false;

	function onClose() {
		modalOpen = false;
	}
</script>

<!-- <button on:click={() => (modalOpen = !modalOpen)}>show video</button> -->

<div id="div1">Div 1</div>
<div id="div2">Div 2</div>

<br />
<button
	on:click={() => (modalOpen = !modalOpen)}
	class="thumbnail relative w-52 aspect-video rounded-2xl"
>
	<div class="absolute w-full h-full z-10 flex justify-center items-center p-8">
		<svg
			class="w-full h-full fill-slate-800"
			xmlns="http://www.w3.org/2000/svg"
			viewBox="0 0 512 512"
		>
			<path
				d="M0 256a256 256 0 1 1 512 0A256 256 0 1 1 0 256zM188.3 147.1c-7.6 4.2-12.3 12.3-12.3 20.9V344c0 8.7 4.7 16.7 12.3 20.9s16.8 4.1 24.3-.5l144-88c7.1-4.4 11.5-12.1 11.5-20.5s-4.4-16.1-11.5-20.5l-144-88c-7.4-4.5-16.7-4.7-24.3-.5z"
			/></svg
		>
	</div>
	<div
		class="thumbnail-mask rounded-2xl absolute bg-white opacity-30 hover:opacity-0 w-full h-full"
	></div>
	<img class="rounded-2xl border border-slate-400 shadow-lg" {src} {alt} />
</button>

{#if modalOpen}
	<div class="  fixed w-full left-0 top-0 h-full z-30 p-3 shadow-2xl bg-white opacity-60" />

	<button
		on:click={onClose}
		class="fixed top-0 left-0 flex justify-center items-center z-30 w-full h-full"
	>
		<div class="aspect-video w-full max-w-2xl">
			<iframe
				class="aspect-video w-full h-full z-40"
				src="https://www.youtube.com/embed/dQw4w9WgXcQ"
				title="YouTube video player"
				frameborder="0"
				allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
				allowfullscreen
			></iframe>
		</div>
	</button>
{/if}

<style>
	/* when div1 is hovered make div2 blue
	body:has(.thumbnail:hover) .thumbnail-mask {
		background: blue !important;
	} */

	/* Default styles for div1 and div2 */
	#div1 {
		background-color: blue;
		padding: 10px;
		color: white;
	}

	#div2 {
		background-color: red;
		padding: 10px;
		color: white;
	}

	/* Styles for div1 when div2 is hovered */
	#div2:hover + #div1 {
		background-color: green;
		color: black;
	}
</style>
