<script lang="ts">
	import { fade } from 'svelte/transition';
	import Header from '$lib/components/header/Header.svelte';
	import AboutUs from '$lib/components/sections/AboutUs.svelte';
	import OurTeam from '$lib/components/sections/OurTeam.svelte';
	import OurServices from '$lib/components/sections/OurServices.svelte';
</script>

<div transition:fade>
	<div class="font-roboto flex min-h-dvh flex-col">
		<Header />

		<main class="flex-auto">
			<AboutUs />
			<OurTeam />
			<OurServices />
		</main>
		<footer>footer</footer>
	</div>
</div>
