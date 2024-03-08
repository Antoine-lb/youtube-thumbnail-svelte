<script>
	import YoutubeVideo from '$lib/YoutubeVideo.svelte';
	import toast from 'svelte-french-toast';

	function copyComponent() {
		toast.success('Component copied!');
	}
</script>

<br />
<br />
<br />

<div class="flex justify-center rotate-3">
	<h1 class="bg-[#FF3E00] text-3xl font-bold text-[#f3f4f0] py-1 px-3 text-center">
		Svelte Thumbnail<br /> Component
	</h1>
</div>
<br />

<p class="font-bold text-center">Video thumbnail</p>
<p class="font-bold text-center">+ hover effect</p>
<p class="font-bold text-center">+ full screen modal</p>
<p class="font-bold text-center">+ svelte</p>
<p class="font-bold text-center">+ tailwind</p>

<br />
<br />
<div class=" flex justify-center">
	<YoutubeVideo src="https://picsum.photos/800/600" alt="youtube video" />
</div>
<br />
<br />
<div class="border-dashed border-2 border-gray-400 max-w-xl m-auto p-5 rounded-3xl">
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

	<img src="iframe-src.webp" alt="iframe src" class="w-full" />

	<br />

	<p>7. Paste that url in the parameter <code>youtubeIFrameSrc</code></p>

	<br />
</div>
<br />
<br />
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
