<script lang="ts">
	import Fade from '$lib/components/Fade.svelte';
	import ArrowRightIcon from '$lib/icons/ArrowRightIcon.svelte';
	import { fade, slide } from 'svelte/transition';

	let { toggleInfo, isShowInfo } = $props();
</script>

<Fade>
	<div class="flex justify-between">
		<div class="color-292424 w-1/2">
			<h6 class="team-title mb-2.5">Младен Бардук</h6>

			<span class="color-cab18a mb-7 inline-block text-xl">Голова адвокатського об'єднання</span>

			<p class="mb-5 text-center 2xl:text-left">
				<span class="font-semibold">Професійний досвід:</span>
				<br class="hidden 2xl:block" />
				Младен Бардук веде адвокатську практику з 2009 року. До цього він працював у суді на різних посадах,
				що надало йому унікальний погляд на юридичні процеси зсередини. Його досвід у поєднанні з багаторічною
				практикою робить його надзвичайно цінним спеціалістом.
			</p>

			<div class="max-lg:hidden">
				<p class="mb-5 text-center 2xl:text-left">
					<span class="font-semibold">Спеціалізація:</span>
					<br class="hidden 2xl:block" />
					Младен спеціалізується у різних галузях права, що дозволяє йому ефективно вирішувати найрізноманітніші
					юридичні питання. Його всебічні знання і вміння охоплюють широкий спектр правових проблем,
					що робить його універсальним юристом.
				</p>

				<p class="mb-5 text-center 2xl:text-left">
					<span class="font-semibold">Особисті якості:</span>
					<br class="hidden 2xl:block" />
					Младен є душею команди та головою нашого адвокатського об'єднання. Його нестандартний підхід
					до вирішення різних питань виділяє його серед інших фахівців. Младен відзначається високим
					професіоналізмом, креативністю та здатністю знаходити унікальні рішення для складних ситуацій.
				</p>

				<p class="text-center 2xl:text-left">
					<span class="font-semibold">Чому обрати Младена:</span>
					<br class="hidden 2xl:block" />
					Чому обрати Младена: Младен Бардук не лише є дуже хорошим спеціалістом, але й лідером, який
					веде свою команду до успіху. Його компетентність, нестандартне мислення та багаторічний досвід
					у правовій сфері гарантують, що клієнти отримують найкращу правову допомогу. З таким адвокатом
					ви можете бути впевнені в успішному вирішенні ваших правових питань.
				</p>
			</div>

			<div class="max-md:visible">
				{#if isShowInfo}
					<div transition:slide>
						<div transition:fade>
							<p class="mb-5 text-center 2xl:text-left">
								<span class="font-semibold">Спеціалізація:</span>
								<br class="hidden 2xl:block" />
								Младен спеціалізується у різних галузях права, що дозволяє йому ефективно вирішувати
								найрізноманітніші юридичні питання. Його всебічні знання і вміння охоплюють широкий спектр
								правових проблем, що робить його універсальним юристом.
							</p>

							<p class="mb-5 text-center 2xl:text-left">
								<span class="font-semibold">Особисті якості:</span>
								<br class="hidden 2xl:block" />
								Младен є душею команди та головою нашого адвокатського об'єднання. Його нестандартний
								підхід до вирішення різних питань виділяє його серед інших фахівців. Младен відзначається
								високим професіоналізмом, креативністю та здатністю знаходити унікальні рішення для складних
								ситуацій.
							</p>

							<p class="text-center 2xl:text-left">
								<span class="font-semibold">Чому обрати Младена:</span>
								<br class="hidden 2xl:block" />
								Чому обрати Младена: Младен Бардук не лише є дуже хорошим спеціалістом, але й лідером,
								який веде свою команду до успіху. Його компетентність, нестандартне мислення та багаторічний
								досвід у правовій сфері гарантують, що клієнти отримують найкращу правову допомогу. З
								таким адвокатом ви можете бути впевнені в успішному вирішенні ваших правових питань.
							</p>
						</div>
					</div>
				{/if}

				<button
					class="cursor-pointer lg:hidden"
					onclick={toggleInfo}
					type="button"
					aria-label={isShowInfo ? 'Показати інформацію' : 'Сховати інформацію'}
					title={isShowInfo ? 'Показати інформацію' : 'Сховати інформацію'}
				>
					{#if isShowInfo}
						<span> Сховати </span>
					{:else}
						<span>
							Читати далі

							<i>
								<ArrowRightIcon />
							</i>
						</span>
					{/if}
				</button>
			</div>
		</div>

		<picture class="max-w-full">
			<source srcset="/img/our-team-six.webp" type="image/webp" />
			<img loading="lazy" width="510" height="596" src="/img/our-team-one.jpg" alt="Team six" />
		</picture>
	</div>
</Fade>
