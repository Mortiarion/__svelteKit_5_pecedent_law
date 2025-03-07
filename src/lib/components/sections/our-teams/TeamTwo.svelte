<script lang="ts">
	import Fade from '$lib/components/Fade.svelte';
	import ArrowRightIcon from '$lib/icons/ArrowRightIcon.svelte';
	import { fade, slide } from 'svelte/transition';

	let { toggleInfo, isShowInfo } = $props();
</script>

<Fade>
	<div class="flex justify-between">
		<div class="color-292424 w-1/2">
			<h6 class="team-title mb-2.5">Віктор Бардук</h6>

			<span class="color-cab18a mb-7 inline-block text-xl"> Адвокат </span>

			<p class="mb-5 text-center 2xl:text-left">
				<span class="font-semibold">Професійний досвід:</span>
				<br class="hidden 2xl:block" />
				Віктор Бардук веде адвокатську практику з 2012 року. До цього він тривалий час працював у правоохоронних
				органах України. Його кар'єра включає посади старшого оперативного уповноваженого в органах карного
				розшуку в складі Міністерства внутрішніх справ України, старшого слідчого та старшого оперативного
				уповноваженого податкової міліції.
			</p>

			<div class="max-lg:hidden">
				<p class="mb-5 text-center 2xl:text-left">
					<span class="font-semibold">Спеціалізація:</span>
					<br class="hidden 2xl:block" />
					Віктор спеціалізується на кримінальному процесі. Завдяки його глибоким знанням та досвіду,
					багато його клієнтів отримали виправдовувальні вироки.
				</p>

				<p class="mb-5 text-center 2xl:text-left">
					<span class="font-semibold">Досвід:</span>
					<br class="hidden 2xl:block" />
					Загальний стаж юридичної роботи Віктора складає понад 25 років, що свідчить про його високу
					компетентність та надійність як адвоката.
				</p>

				<p class="text-center 2xl:text-left">
					<span class="font-semibold">Чому обрати Віктора:</span>
					<br class="hidden 2xl:block" />
					З таким адвокатом ви під надійним захистом. Віктор Бардук забезпечує професійний підхід та
					індивідуальну увагу до кожного клієнта, що гарантує успішний результат справи.
				</p>
			</div>

			<div class="max-md:visible">
				{#if isShowInfo}
					<div transition:slide>
						<div transition:fade>
							<p class="mb-5 text-center 2xl:text-left">
								<span class="font-semibold">Спеціалізація:</span>
								<br class="hidden 2xl:block" />
								Віктор спеціалізується на кримінальному процесі. Завдяки його глибоким знанням та досвіду,
								багато його клієнтів отримали виправдовувальні вироки.
							</p>

							<p class="mb-5 text-center 2xl:text-left">
								<span class="font-semibold">Досвід:</span>
								<br class="hidden 2xl:block" />
								Загальний стаж юридичної роботи Віктора складає понад 25 років, що свідчить про його
								високу компетентність та надійність як адвоката.
							</p>

							<p class="text-center 2xl:text-left">
								<span class="font-semibold">Чому обрати Віктора:</span>
								<br class="hidden 2xl:block" />
								З таким адвокатом ви під надійним захистом. Віктор Бардук забезпечує професійний підхід
								та індивідуальну увагу до кожного клієнта, що гарантує успішний результат справи.
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
			<source srcset="/img/our-team-two.webp" type="image/webp" />
			<img loading="lazy" width="510" height="596" src="/img/our-team-two.jpg" alt="Team two" />
		</picture>
	</div>
</Fade>
