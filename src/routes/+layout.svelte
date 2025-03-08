<script lang="ts">
	import { fade } from 'svelte/transition';

	import '../app.css';

	import Header from '$lib/components/header/Header.svelte';
	import Footer from '$lib/components/footer/Footer.svelte';

	let { children } = $props();
</script>

<div transition:fade>
	<div class="font-roboto flex min-h-dvh flex-col">
		<Header />

		{@render children()}

		<Footer />
	</div>
</div>
