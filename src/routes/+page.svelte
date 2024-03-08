<script>
	import YoutubeThumbnail from '$lib/YoutubeThumbnail.svelte';
	import toast from 'svelte-french-toast';

	async function copyComponent() {
		const response = await fetch('YoutubeThumbnail.txt');
		const text = await response.text();
		console.log('text', text);

		navigator.clipboard.writeText(text);

		toast.success('Component copied!');
	}
</script>

<svelte:head>
	<title>Youtube Thumbnail Svelte</title>
	<meta name="description" content="Youtube Thumbnail Svelte" />
	<meta name="keywords" content="svelte, youtube, thumbnail, component" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	<meta name="robots" content="index, follow" />
	<meta name="theme-color" content="#FF3E00" />
</svelte:head>

<div class="bg-[#FF3E00] h-1 fixed w-full z-50 shadow-lg"></div>
<br />
<br />
<div class="flex justify-center">
	<h1 class=" text-3xl font-bold text-[#333] py-1 px-3 text-center">
		Svelte Youtube <br /> Thumbnail Component
	</h1>
</div>
<br />

<div class="max-w-[22rem] m-auto">
	<img src="/try-it.svg" alt="try it text with arrow" class="w-20" />
</div>
<div class=" flex justify-center">
	<YoutubeThumbnail alt="youtube video" />
</div>
<br />
<br />
<p class="font-bold text-center text-[#333] text-lg">Thumbnail + full screen modal</p>
<p class="font-bold text-center text-[#333] text-lg">made with</p>
<p class="font-bold text-center text-[#333] text-lg">Svelte + Tailwind</p>
<br />
<div class="border-dashed border-4 border-gray-300 max-w-xl m-auto p-5 rounded-3xl">
	<p>How to use:</p>
	<p>1. Create <code>YoutubeThumbnail.svelte</code> in your <code>lib</code> folder</p>
	<p>2. Copy and paste the component:</p>
	<br />
	<div class="flex justify-center">
		<button
			class="figma_video-button hover:bg-[#fafafa] transition-all text-[#333] text-xl"
			on:click={copyComponent}
		>
			<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" class="mr-1 h-6 fill-[#333]">
				<path
					d="M64 464H288c8.8 0 16-7.2 16-16V384h48v64c0 35.3-28.7 64-64 64H64c-35.3 0-64-28.7-64-64V224c0-35.3 28.7-64 64-64h64v48H64c-8.8 0-16 7.2-16 16V448c0 8.8 7.2 16 16 16zM224 304H448c8.8 0 16-7.2 16-16V64c0-8.8-7.2-16-16-16H224c-8.8 0-16 7.2-16 16V288c0 8.8 7.2 16 16 16zm-64-16V64c0-35.3 28.7-64 64-64H448c35.3 0 64 28.7 64 64V288c0 35.3-28.7 64-64 64H224c-35.3 0-64-28.7-64-64z"
				/></svg
			> Copy component
		</button>
	</div>
	<br />
	<p>3. Find the Youtube Video you want to put on your site</p>
	<p>4. Click the share button</p>
	<p>5. Click "Embed"</p>
	<p>6. DON'T copy the entire text, but only the url inside of <code>src</code></p>
	<br />

	<img src="iframe-src.webp" alt="iframe src" class="w-full rounded" />

	<br />

	<p>7. Paste that url in the parameter <code>youtubeIFrameSrc</code></p>

	<br />
</div>
<br />
<br />
<br />

<footer class="text-center py-10">
	<a class="underline" href="https://github.com/Antoine-lb/youtube-thumbnail-svelte" target="_blank"
		>https://github.com/Antoine-lb/youtube-thumbnail-svelte</a
	>
</footer>

<br />
<br />
<br />

<style>
	body {
		background-color: #f3f4f0;
	}

	.figma_video-button {
		display: inline-flex;
		padding: 10px var(--Section-Margin, 24px);

		justify-content: center;
		align-items: center;
		gap: var(--Element-Spacing, 8px);
		border-radius: 32px;
		border: 1px solid var(--Colors-Grey-400, #bcc3c8);
		box-shadow:
			0px 0px 4px 2px rgba(22, 22, 22, 0.057),
			0px -1px 2px 2px rgba(22, 22, 22, 0.08) inset,
			0px 1px 2px 2px rgba(255, 255, 255, 0.12) inset;
	}
</style>
