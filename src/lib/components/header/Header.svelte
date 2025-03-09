<script lang="ts">
	import { onMount, onDestroy } from 'svelte';
	import Location from './components/Location.svelte';
	import Logo from './components/Logo.svelte';
	import NavigationMenu from './components/NavigationMenuLink.svelte';
	import SocialMenuLink from './components/SocialMenuLink.svelte';
	import { slide } from 'svelte/transition';

	let isHidden = $state(false);
	const scrollThreshold = 300;
	let lastScrollY = 0;
	let ticking = false;
	let timeoutId: number | null = null;
	let forceCheckInterval: number | null = null;

	function handleScroll() {
		if (ticking) return;

		window.requestAnimationFrame(() => {
			const currentScrollY = window.scrollY;
			const scrollDifference = currentScrollY - lastScrollY;

			// Додали перевірку для малих змін (10px)
			if (Math.abs(scrollDifference) > 10) {
				// Скрол вниз → ховаємо
				if (currentScrollY > scrollThreshold && scrollDifference > 0) {
					if (!isHidden) isHidden = true;
				} 
				// Скрол вверх → показуємо (з невеликою затримкою)
				else if (currentScrollY < scrollThreshold && scrollDifference < 0) {
					if (isHidden) {
						if (timeoutId) clearTimeout(timeoutId);
						timeoutId = setTimeout(() => (isHidden = false), 200);
					}
				}
			}

			lastScrollY = currentScrollY;
			ticking = false;
		});

		ticking = true;
	}

	// Додаємо перевірку кожні 200ms (щоб спрацювало навіть при повільному скролі)
	function startForceCheck() {
		forceCheckInterval = setInterval(() => {
			handleScroll();
		}, 200);
	}

	onMount(() => {
		window.addEventListener('scroll', handleScroll);
		startForceCheck();

		return () => {
			window.removeEventListener('scroll', handleScroll);
			if (timeoutId) clearTimeout(timeoutId);
			if (forceCheckInterval) clearInterval(forceCheckInterval);
		};
	});
</script>

<header class="bg-header-img sticky top-0 z-10 text-white">
	<div class="container">
		<nav class="flex items-center pt-7 pb-4">
			<Logo />
			<NavigationMenu />
			<SocialMenuLink />
		</nav>

		{#if !isHidden}
			<div class="mb-14" transition:slide>
				<Location />
			</div>
		{/if}
	</div>
</header>
