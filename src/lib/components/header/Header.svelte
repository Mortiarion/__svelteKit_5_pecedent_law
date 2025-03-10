<script lang="ts">
	import { onMount, onDestroy } from 'svelte';
	import Location from './components/Location.svelte';
	import Logo from './components/Logo.svelte';
	import NavigationMenu from './components/NavigationMenuLink.svelte';
	import SocialMenuLink from './components/SocialMenuLink.svelte';
	import { slide, fade } from 'svelte/transition';

	let isShowLocation = true;
	let lastScrollY = window.scrollY;
	let scrollDirection = "up"; // "up" | "down"
	let scrollTimeout: number;
	let isAnimating = false;

	function handleScroll() {
		const currentScrollY = window.scrollY;
		const scrollDiff = currentScrollY - lastScrollY;

		// Визначаємо напрямок
		if (scrollDiff > 0) {
			scrollDirection = "down";
		} else if (scrollDiff < 0) {
			scrollDirection = "up";
		}

		// Debounce - щоб не було зайвих викликів
		clearTimeout(scrollTimeout);
		scrollTimeout = setTimeout(() => {
			// Логіка показу / приховування
			if (scrollDirection === "down" && currentScrollY >= 200 && !isAnimating) {
				isAnimating = true;
				isShowLocation = false;
				setTimeout(() => (isAnimating = false), 500); // Блокуємо зміну стану на 500мс
			} else if (scrollDirection === "up" && currentScrollY < 200 && !isAnimating) {
				isAnimating = true;
				isShowLocation = true;
				setTimeout(() => (isAnimating = false), 500);
			}

			lastScrollY = currentScrollY;
		}, 100); // Затримка 100 мс
	}

	onMount(() => {
		window.addEventListener('scroll', handleScroll);
		return () => {
			window.removeEventListener('scroll', handleScroll);
			clearTimeout(scrollTimeout);
		};
	});
</script>

<header class="bg-header-img sticky top-0 z-10 text-white">
	<div class="relative container">
		<nav class="flex items-center pt-7 pb-4">
			<Logo />
			<NavigationMenu />
			<SocialMenuLink />
		</nav>
		<!-- <button onclick={toggleLocation}>/sdafdsaf</button> -->
		{#if isShowLocation}
			<div class="mb-14" transition:slide>
				<div transition:fade>
					<Location />
				</div>
			</div>
		{/if}
	</div>
</header>
