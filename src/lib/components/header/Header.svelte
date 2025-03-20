<script lang="ts">
	import { onDestroy, onMount } from 'svelte';
	import Location from './components/Location.svelte';
	import Logo from './components/Logo.svelte';
	import NavigationMenu from './components/NavigationMenuLink.svelte';
	import SocialMenuLink from './components/SocialMenuLink.svelte';
	import { slide, fade } from 'svelte/transition';

	let isLocation = $state(true);

	let isBurger = $state(false);
	let btn: HTMLElement;

	function toggleBurger() {
		isBurger = !isBurger;

		if (isBurger) {
			btn.classList.add('open');
		} else {
			btn.classList.remove('open');
		}
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

		if (window.innerWidth >= 1024) {
			isBurger = true;
		}
	});
</script>

<header class="bg-header-img sticky top-0 z-10 text-white">
	<div class="container">
		<nav class="relative mt-7 mb-4 flex max-lg:flex-col">
			<button
				bind:this={btn}
				class="burger absolute top-7 left-0 hidden h-6 w-6 cursor-pointer max-lg:flex max-lg:flex-col max-lg:gap-1.5"
				type="button"
				aria-label={isBurger ? ' Сховати' : 'Показати'}
				title={isBurger ? ' Сховати' : 'Показати'}
				onclick={toggleBurger}
				class:is-open={isBurger}
			>
				<div class="line h-0.5 rounded-full w-full bg-white transition-transform duration-300"></div>
				<div class="line h-0.5 rounded-full w-full bg-white transition-transform duration-300"></div>
				<div class="line h-0.5 rounded-full w-full bg-white transition-transform duration-300"></div>
			</button>

			<Logo />

			{#if isBurger}
				<div class="ml-auto max-lg:ml-0 max-lg:mt-5" transition:slide>
					<div
						class="flex flex-wrap justify-end gap-5 max-lg:flex-col max-lg:gap-7"
						transition:fade
					>
						<NavigationMenu />
						<SocialMenuLink />

						<div class="hidden max-lg:block">
							<Location />
						</div>
					</div>
				</div>
			{/if}
		</nav>

		{#if isLocation}
			<div class="mb-14 max-lg:mb-7 max-lg:hidden" transition:slide>
				<div transition:fade>
					<Location />
				</div>
			</div>
		{/if}
	</div>
</header>

<style lang="postcss">
	

	.burger.is-open .line:nth-child(1) {
		transform: translateY(8px) rotate(45deg);
	}

	.burger.is-open .line:nth-child(2) {
		opacity: 0;
	}

	.burger.is-open .line:nth-child(3) {
		transform: translateY(-8px) rotate(-45deg);
	}
</style>
