<script lang="ts">
	import Fade from '$lib/components/Fade.svelte';
	import ArrowRightIcon from '$lib/icons/ArrowRightIcon.svelte';
	import { fade, slide } from 'svelte/transition';

	let { toggleInfo, isShowInfo } = $props();
</script>

<Fade>
	<div class="team-container-reverse ">
		<div class="color-292424 w-1/2 max-lg:w-full max-lg:text-center">
			<h6 class="team-title">Віктор Бардук</h6>

			<span class="team-subtitle"> Адвокат </span>

			<p class="our-team-p">
				<span class="font-semibold">Професійний досвід:</span>
				<br />
				Віктор Бардук веде адвокатську практику з 2012 року. До цього він тривалий час працював у правоохоронних
				органах України. Його кар'єра включає посади старшого оперативного уповноваженого в органах карного
				розшуку в складі Міністерства внутрішніх справ України, старшого слідчого та старшого оперативного
				уповноваженого податкової міліції.
			</p>

			<div class="max-xl:hidden">
				<p class="our-team-p">
					<span class="font-semibold">Спеціалізація:</span>
					<br />
					Віктор спеціалізується на кримінальному процесі. Завдяки його глибоким знанням та досвіду,
					багато його клієнтів отримали виправдовувальні вироки.
				</p>

				<p class="our-team-p">
					<span class="font-semibold">Досвід:</span>
					<br />
					Загальний стаж юридичної роботи Віктора складає понад 25 років, що свідчить про його високу
					компетентність та надійність як адвоката.
				</p>

				<p class="our-team-p">
					<span class="font-semibold">Чому обрати Віктора:</span>
					<br />
					З таким адвокатом ви під надійним захистом. Віктор Бардук забезпечує професійний підхід та
					індивідуальну увагу до кожного клієнта, що гарантує успішний результат справи.
				</p>
			</div>

			<div class="max-md:visible">
				{#if isShowInfo}
					<div transition:slide>
						<div class="flex flex-col" transition:fade>
							<p class="our-team-p">
								<span class="font-semibold">Спеціалізація:</span>
								<br />
								Віктор спеціалізується на кримінальному процесі. Завдяки його глибоким знанням та досвіду,
								багато його клієнтів отримали виправдовувальні вироки.
							</p>

							<p class="our-team-p">
								<span class="font-semibold">Досвід:</span>
								<br />
								Загальний стаж юридичної роботи Віктора складає понад 25 років, що свідчить про його
								високу компетентність та надійність як адвоката.
							</p>

							<p class="our-team-p">
								<span class="font-semibold">Чому обрати Віктора:</span>
								<br />
								З таким адвокатом ви під надійним захистом. Віктор Бардук забезпечує професійний підхід
								та індивідуальну увагу до кожного клієнта, що гарантує успішний результат справи.
							</p>
						</div>
					</div>
				{/if}

				<button
					class="cursor-pointer xl:hidden"
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
			<img
				class="team-img"
				loading="lazy"
				width="510"
				height="596"
				src="/img/our-team-two.jpg"
				alt="Team two"
			/>
		</picture>
	</div>
</Fade>
