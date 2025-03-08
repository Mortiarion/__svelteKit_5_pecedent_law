<script lang="ts">
	import Location from './components/Location.svelte';
	import Logo from './components/Logo.svelte';
	import NavigationMenu from './components/NavigationMenuLink.svelte';
	import SocialMenuLink from './components/SocialMenuLink.svelte';
</script>

<header class="bg-header-img text-white">
	<div class="container">
		<nav class="flex items-center pt-7 pb-4">
			<Logo />
			<NavigationMenu />
			<SocialMenuLink />
		</nav>

		<hr class="color-5c524b mb-6" />

		<Location />
	</div>
</header>
