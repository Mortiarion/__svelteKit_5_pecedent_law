<script lang="ts">
	import Fade from '$lib/components/Fade.svelte';
	import ArrowRightIcon from '$lib/icons/ArrowRightIcon.svelte';
	import { fade, slide } from 'svelte/transition';

	let { toggleInfo, isShowInfo } = $props();
</script>

<Fade>
	<div class="team-container">
		<picture class="max-w-full">
			<source srcset="/img/our-team-one.webp" type="image/webp" />
			<img
				class="team-img"
				loading="lazy"
				width="510"
				height="596"
				src="/img/our-team-one.jpg"
				alt="Team one"
			/>
		</picture>

		<div class="color-292424 w-1/2 max-lg:w-full max-lg:text-center">
			<h6 class="team-title">Діана Лісіна</h6>

			<span class="team-subtitle"> Адвокат </span>

			<p class="our-team-p">
				<span class="font-semibold">Професійний досвід:</span>
				<br />
				Діана Лісіна веде адвокатську практику з початку 2022 року. Незважаючи на відносно короткий термін
				професійної діяльності, вона вже встигла зарекомендувати себе як висококваліфікований фахівець.
			</p>

			<div class="max-lg:hidden">
				<p class="our-team-p">
					<span class="font-semibold">Спеціалізація:</span>
					<br />
					Діана спеціалізується на корпоративних спорах та договірному праві,а також на судових процесах
					з адміністративного права. Її експертні знання та досвід допомогли врятувати не одне підприємство
					від правових труднощів.
				</p>

				<p class="our-team-p">
					<span class="font-semibold">Особисті якості:</span>
					<br />
					Нехай Вас не бентежить вік та привабливість Діани. Вона є відмінним спеціалістом, яка відзначається
					виконавчістю, чесністю та порядністю. Її професіоналізм, уважність до деталей та відданість
					своїй роботі забезпечують успішний результат кожної справи, якою вона займається.
				</p>

				<p class="our-team-p">
					<span class="font-semibold">Чому обрати Діану:</span>
					<br />
					Діана Лісіна - це надійний партнер у вирішенні юридичних питань.Її компетентність, відповідальність
					та прагнення досягати найкращих результатів роблять її незамінною для клієнтів, які шукають
					надійну правову підтримку.
				</p>
			</div>

			<div class="max-md:visible">
				{#if isShowInfo}
					<div transition:slide>
						<div transition:fade>
							<p class="our-team-p">
								<span class="font-semibold">Спеціалізація:</span>
								<br />
								Діана спеціалізується на корпоративних спорах та договірному праві,а також на судових
								процесах з адміністративного права. Її експертні знання та досвід допомогли врятувати
								не одне підприємство від правових труднощів.
							</p>

							<p class="our-team-p">
								<span class="font-semibold">Особисті якості:</span>
								<br />
								Нехай Вас не бентежить вік та привабливість Діани. Вона є відмінним спеціалістом, яка
								відзначається виконавчістю, чесністю та порядністю. Її професіоналізм, уважність до деталей
								та відданість своїй роботі забезпечують успішний результат кожної справи, якою вона займається.
							</p>

							<p class="our-team-p">
								<span class="font-semibold">Чому обрати Діану:</span>
								<br />
								Діана Лісіна - це надійний партнер у вирішенні юридичних питань.Її компетентність, відповідальність
								та прагнення досягати найкращих результатів роблять її незамінною для клієнтів, які шукають
								надійну правову підтримку.
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
