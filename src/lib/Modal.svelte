<script lang="ts">
	import type { MouseEventHandler } from 'svelte/elements';

	export let onClose: MouseEventHandler<HTMLButtonElement>;
</script>

<div
	on:click={onClose}
	class=" bg-white opacity-40 fixed w-full left-0 top-0 h-full z-30 p-3 shadow-2xl"
/>

<!-- <div class="flex flex-row z-50 sticky top-4 left-3 p-4">
        <button
            on:click={onClose}
            class="p-3 rounded-full font-bold text-2xl w-[4rem] shadow-lg z-10 backdrop-blur-2xl border-[2px] border-slate-700"
            style="background-color: #ffffff99;"
        >
            <svg
                xmlns="http://www.w3.org/2000/svg"
                height="1.6em"
                class="fill-slate-700"
                viewBox="0 0 448 512"
            >
                <path
                    d="M9.4 233.4c-12.5 12.5-12.5 32.8 0 45.3l160 160c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L109.2 288 416 288c17.7 0 32-14.3 32-32s-14.3-32-32-32l-306.7 0L214.6 118.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0l-160 160z"
                /></svg
            >
        </button>
    </div> -->
<div
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
</div>
