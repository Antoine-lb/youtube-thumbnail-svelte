<script lang="ts">
	import { onMount } from 'svelte';
	import '../app.css';

	import { Toaster } from 'svelte-french-toast';
</script>

<Toaster />

<slot />
