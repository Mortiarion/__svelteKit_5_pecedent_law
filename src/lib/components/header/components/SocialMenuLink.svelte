<script lang="ts">
	import FacebookIcon from '$lib/icons/FacebookIcon.svelte';
	import GmailIcon from '$lib/icons/GmailIcon.svelte';
	import InstagramIcon from '$lib/icons/InstagramIcon.svelte';
	import TelegramIcon from '$lib/icons/TelegramIcon.svelte';
	import TelephoneIcon from '$lib/icons/TelephoneIcon.svelte';
	import TiktokIcon from '$lib/icons/TiktokIcon.svelte';
	import ViberIcon from '$lib/icons/ViberIcon.svelte';
</script>

<ul class="flex gap-5 items-centerb ml-20">
	<li>
		<a href="tel:+380930343344" title="Зателефонуйте нам" aria-label="Зателефонуйте нам">
			<TelephoneIcon />
		</a>
	</li>

	<li>
		<a href="https://t.me/Justitia_od" title="Ми в телеграмі" aria-label="Ми в телеграмі">
			<TelegramIcon />
		</a>
	</li>

	<li>
		<a href="viber://chat?number=%2B380930343344" title="Ми в вайбері" aria-label="Ми в вайбері">
			<ViberIcon />
		</a>
	</li>

	<li>
		<a href="mailto:precedent.prava@gmail.com" title="Напишіть нам" aria-label="Напишіть нам">
			<GmailIcon />
		</a>
	</li>

	<li>
		<a href="https://www.instagram.com/legal_precedent_/" title="Ми в інстаграм" aria-label="Ми в інстаграм">
			<InstagramIcon />
		</a>
	</li>

	<li>
		<a href="https://www.facebook.com/centrjurisprudence" title="Ми в фейсбук" aria-label="Ми в фейсбук">
			<FacebookIcon />
		</a>
	</li>

	<li>
		<a href="https://vm.tiktok.com/ZMrLcTjHX" title="Ми в тікток" aria-label="Ми в тікток">
			<TiktokIcon />
		</a>
	</li>
</ul>
