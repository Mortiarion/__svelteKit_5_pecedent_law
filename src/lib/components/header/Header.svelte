<script lang="ts">
	import { onDestroy, onMount } from 'svelte';
	import Location from './components/Location.svelte';
	import Logo from './components/Logo.svelte';
	import NavigationMenu from './components/NavigationMenuLink.svelte';
	import SocialMenuLink from './components/SocialMenuLink.svelte';
	import { slide, fade } from 'svelte/transition';
	import BurgerIcon from '$lib/icons/BurgerIcon.svelte';
	
	let isLocation = $state(true);

	let isBurger = $state(false);

	function toggleBurger() {
		isBurger = !isBurger;
	}

	onMount(() => {
		const aboutUsSection = document.getElementById('about-us');

		if (aboutUsSection) {
			const observer = new IntersectionObserver(
				([entry]) => {
					isLocation = entry.isIntersecting;
				},
				{ threshold: 0.1 }
			);

			observer.observe(aboutUsSection);

			onDestroy(() => observer.disconnect());
		}
	});
</script>

<header class="bg-header-img sticky top-0 z-10 text-white">
	<div class="container hidden max-lg:block">
		<nav class="mt-7 mb-4 flex flex-col">
			<div class="relative flex justify-center">

				<button class=" absolute left-0 top-1/3" type="button" aria-label="Показати" title="Показати" onclick={toggleBurger}>
					<i>
						<BurgerIcon />
					</i>
				</button>
	
				<Logo />
			</div>

			{#if isBurger}
				<div transition:slide>
					<div transition:fade>
						<NavigationMenu />
						<Location />
						<SocialMenuLink />
					</div>
				</div>
			{/if}
		</nav>
	
	</div>

	<div class="relative container max-lg:hidden">
		<nav class="mt-7 mb-4 flex flex-wrap items-center lg:mt-5">
			<Logo />
			<NavigationMenu />
			<SocialMenuLink />
		</nav>

		{#if isLocation}
			<div class="mb-14 max-lg:mb-7" transition:slide>
				<div transition:fade>
					<Location />
				</div>
			</div>
		{/if}
	</div>
</header>
