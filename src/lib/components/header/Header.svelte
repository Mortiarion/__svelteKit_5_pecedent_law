<script lang="ts">
	import { onMount } from 'svelte';
	import Location from './components/Location.svelte';
	import Logo from './components/Logo.svelte';
	import NavigationMenu from './components/NavigationMenuLink.svelte';
	import SocialMenuLink from './components/SocialMenuLink.svelte';
	import { slide } from 'svelte/transition';

	let startScrolly = $state(0);
	let isHidden = $state(true);
	let scrollThreshold = $state(300);
	let minScrollDistance = $state(20);

	function handleScroll() {
		const currentScrolly = Math.round(window.scrollY);
		console.log('start scroll', currentScrolly);
		if (Math.abs(currentScrolly - startScrolly) > minScrollDistance) {
			startScrolly = currentScrolly;
			console.log('if cur scroll',currentScrolly);
			if (currentScrolly > scrollThreshold) {
				isHidden = false;
			} else {
				isHidden = true;
			}
		}
		startScrolly = currentScrolly;
	}

	onMount(() => {
		window.addEventListener('scroll', handleScroll);

		return () => window.removeEventListener('scroll', handleScroll);
	});
</script>

<header class="bg-header-img sticky top-0 z-10 text-white">
	<div class="container">
		<nav class="flex items-center pt-7 pb-4">
			<Logo />
			<NavigationMenu />
			<SocialMenuLink />
		</nav>

		{#if isHidden}
			<div class="mb-14" transition:slide>
				<Location />
			</div>
		{/if}
	</div>
</header>
