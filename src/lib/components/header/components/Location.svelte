<script lang="ts">
	import LocationIcon from '$lib/icons/LocationIcon.svelte';
</script>

<hr class="color-5c524b mb-6" />

<div class="flex gap-3">
	<i>
		<LocationIcon />
	</i>

	<div class="flex flex-col">
		<span class="color-cab18a max-md:text-sm"> Місцезнаходження </span>

		<a
			class="font-source text-3xl font-semibold max-lg:text-2xl max-md:text-xl"
			target="_blank"
			title="Подивитись на мапі"
			aria-label="Подивитись на мапі"
			rel="noopener noreferrer"
			href="https://maps.app.goo.gl/ggpQcKQ3uoqvnwid9">м.Одеса вул.Канатна, 68</a
		>
	</div>
</div>
