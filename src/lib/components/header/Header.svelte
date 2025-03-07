<script lang="ts">
	import LocationIcon from "$lib/icons/LocationIcon.svelte";
	import Logo from "./component/Logo.svelte";
	import NavigationMenu from "./component/NavigationMenuLink.svelte";
	import SocialMenuLink from "./component/SocialMenuLink.svelte";
</script>

<header class="bg-header-img text-white">
    <div class="container">
        <nav class="flex items-center pt-7 pb-4">
            <Logo />
            <NavigationMenu />
            <SocialMenuLink />
        </nav>

        <hr class='color-5c524b mb-6'>

        <div class="flex gap-3 mb-14">
            <i>
                <LocationIcon />
            </i>

            <div class="flex flex-col">
                <span class='color-cab18a'>
                    Місцезнаходження
                </span>

                <span class="font-source font-semibold text-3xl">
                    м.Одеса вул.Канатна, 68
                </span>
            </div>
        </div>
    </div>
</header>