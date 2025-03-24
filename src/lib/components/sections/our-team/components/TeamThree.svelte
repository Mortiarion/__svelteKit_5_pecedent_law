<script lang="ts">
	import Fade from '$lib/components/Fade.svelte';
	import ArrowRightIcon from '$lib/icons/ArrowRightIcon.svelte';
	import { fade, slide } from 'svelte/transition';

	let { toggleInfo, isShowInfo } = $props();
</script>

<Fade>
	<div class="team-container">
		<picture class="max-w-full">
			<source srcset="/img/our-team-three.webp" type="image/webp" />
			<img
				class="team-img"
				loading="lazy"
				width="510"
				height="596"
				src="/img/our-team-three.jpg"
				alt="Team three"
			/>
		</picture>

		<div class="color-292424 w-1/2 max-lg:w-full max-lg:text-center">
			<h6 class="team-title">Дмитро Попроцький</h6>

			<span class="team-subtitle"> Адвокат </span>

			<p class="our-team-p">
				<span class="font-semibold">Професійний досвід:</span>
				<br />
				Дмитро Попроцький веде адвокатську практику з 2008 року. За цей час він здобув значний досвід
				у різних галузях права, зокрема у господарському, цивільному та сімейному праві.
			</p>

			<div class="max-xl:hidden">
				<p class="our-team-p">
					<span class="font-semibold">Спеціалізація:</span>
					<br />
					Дмитро спеціалізується на господарському та цивільному судових процесах, допомагаючи клієнтам
					ефективно вирішувати правові питання, пов'язані з бізнесом та особистими справами.
				</p>

				<p class="our-team-p">
					<span class="font-semibold">Чому обрати Дмитра:</span>
					<br />
					Завдяки багаторічному досвіду та глибоким знанням, Дмитро Попроцький пропонує своїм клієнтам
					професійний підхід та надійну правову підтримку. Його компетентність і відповідальність гарантують
					успішне вирішення навіть найскладніших юридичних питань.
				</p>
			</div>

			<div class="max-md:visible">
				{#if isShowInfo}
					<div transition:slide>
						<div class="flex flex-col" transition:fade>
							<p class="our-team-p">
								<span class="font-semibold">Спеціалізація:</span>
								<br />
								Дмитро спеціалізується на господарському та цивільному судових процесах, допомагаючи
								клієнтам ефективно вирішувати правові питання, пов'язані з бізнесом та особистими справами.
							</p>

							<p class="our-team-p">
								<span class="font-semibold">Чому обрати Дмитра:</span>
								<br />
								Завдяки багаторічному досвіду та глибоким знанням, Дмитро Попроцький пропонує своїм клієнтам
								професійний підхід та надійну правову підтримку. Його компетентність і відповідальність
								гарантують успішне вирішення навіть найскладніших юридичних питань.
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
	</div>
</Fade>
