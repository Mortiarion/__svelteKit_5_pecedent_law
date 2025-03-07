<script lang="ts">
	import Fade from '$lib/components/Fade.svelte';
	import ArrowRightIcon from '$lib/icons/ArrowRightIcon.svelte';
	import { fade, slide } from 'svelte/transition';

	let { toggleInfo, isShowInfo } = $props();
</script>

<Fade>
	<div class="flex justify-between">
		<picture class="max-w-full">
			<source srcset="/img/our-team-three.webp" type="image/webp" />
			<img loading="lazy" width="510" height="596" src="/img/our-team-three.jpg" alt="Team three" />
		</picture>

		<div class="color-292424 w-1/2">
			<h6 class="team-title mb-2.5">Дмитро Попроцький</h6>

			<span class="color-cab18a mb-7 inline-block text-xl"> Адвокат </span>

			<p class="mb-5 text-center 2xl:text-left">
				<span class="font-semibold">Професійний досвід:</span>
				<br class="hidden 2xl:block" />
				Дмитро Попроцький веде адвокатську практику з 2008 року. За цей час він здобув значний досвід
				у різних галузях права, зокрема у господарському, цивільному та сімейному праві.
			</p>

			<div class="max-lg:hidden">
				<p class="mb-5 text-center 2xl:text-left">
					<span class="font-semibold">Спеціалізація:</span>
					<br class="hidden 2xl:block" />
					Дмитро спеціалізується на господарському та цивільному судових процесах, допомагаючи клієнтам
					ефективно вирішувати правові питання, пов'язані з бізнесом та особистими справами.
				</p>

				<p class="text-center 2xl:text-left">
					<span class="font-semibold">Чому обрати Дмитра:</span>
					<br class="hidden 2xl:block" />
					Завдяки багаторічному досвіду та глибоким знанням, Дмитро Попроцький пропонує своїм клієнтам
					професійний підхід та надійну правову підтримку. Його компетентність і відповідальність гарантують
					успішне вирішення навіть найскладніших юридичних питань.
				</p>
			</div>

			<div class="max-md:visible">
				{#if isShowInfo}
					<div transition:slide>
						<div transition:fade>
							<p class="mb-5 text-center 2xl:text-left">
								<span class="font-semibold">Спеціалізація:</span>
								<br class="hidden 2xl:block" />
								Дмитро спеціалізується на господарському та цивільному судових процесах, допомагаючи
								клієнтам ефективно вирішувати правові питання, пов'язані з бізнесом та особистими справами.
							</p>

							<p class="text-center 2xl:text-left">
								<span class="font-semibold">Чому обрати Дмитра:</span>
								<br class="hidden 2xl:block" />
								Завдяки багаторічному досвіду та глибоким знанням, Дмитро Попроцький пропонує своїм клієнтам
								професійний підхід та надійну правову підтримку. Його компетентність і відповідальність
								гарантують успішне вирішення навіть найскладніших юридичних питань.
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
	</div>
</Fade>
