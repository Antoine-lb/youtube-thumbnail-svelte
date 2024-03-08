<script lang="ts">
	export let thumbnailSrc: string = 'https://picsum.photos/800/600';
	export let youtubeIFrameSrc: string = 'https://www.youtube.com/embed/dQw4w9WgXcQ';
	export let alt: string | null = 'Youtube thumbnail';
	export let autoplay: boolean = true;

	let modalOpen = false;
	let isHovering = false;

	let videoUrl = youtubeIFrameSrc + '?autoplay=' + (autoplay ? 1 : 0);
</script>

<button
	on:click={() => (modalOpen = !modalOpen)}
	on:mouseover={() => (isHovering = true)}
	on:mouseleave={() => (isHovering = false)}
	on:focus={() => (isHovering = true)}
	class="thumbnail relative w-56 aspect-[3/2] rounded-3xl overflow-hidden shadow-lg border border-slate-300"
>
	<!-- play icon -->
	<div
		class="absolute w-full h-full z-10 flex justify-center items-center transition-all duration-300 ease-in-out"
	>
		<svg
			class="h-[4.5rem] w-[4.5rem] fill-slate-900 transition-all duration-300 ease-in-out"
			xmlns="http://www.w3.org/2000/svg"
			viewBox="0 0 512 512"
			class:!h-16={isHovering}
			class:!w-16={isHovering}
		>
			<path
				d="M0 256a256 256 0 1 1 512 0A256 256 0 1 1 0 256zM188.3 147.1c-7.6 4.2-12.3 12.3-12.3 20.9V344c0 8.7 4.7 16.7 12.3 20.9s16.8 4.1 24.3-.5l144-88c7.1-4.4 11.5-12.1 11.5-20.5s-4.4-16.1-11.5-20.5l-144-88c-7.4-4.5-16.7-4.7-24.3-.5z"
			/>
		</svg>
	</div>

	<!-- thumbnail mask -->
	<div
		class="thumbnail-mask absolute bg-slate-300 opacity-30 w-full h-full transition-all duration-300 ease-in-out"
		class:!opacity-0={isHovering}
	></div>

	<!-- thumbnail -->
	<img class="" src={thumbnailSrc} {alt} />
</button>

{#if modalOpen}
	<!-- modal background opacity -->
	<div class="  fixed w-full left-0 top-0 h-full z-30 p-3 shadow-2xl bg-white opacity-60" />
	<button
		on:click={() => (modalOpen = !modalOpen)}
		class="fixed top-0 left-0 flex justify-center items-center z-30 w-full h-full"
	>
		<div class="aspect-video w-full max-w-2xl">
			<iframe
				class="aspect-video w-full h-full z-40"
				src={videoUrl}
				title="YouTube video player"
				frameborder="0"
				allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
				allowfullscreen
			></iframe>
		</div>
	</button>
{/if}
