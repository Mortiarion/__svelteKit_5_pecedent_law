<script lang="ts">
	import Fade from '$lib/components/Fade.svelte';
	import ArrowRightIcon from '$lib/icons/ArrowRightIcon.svelte';
	import { fade, slide } from 'svelte/transition';

	let { toggleInfo, isShowInfo } = $props();
</script>

<Fade>
	<div class="team-container-reverse ">
		<div class="color-292424 w-1/2 max-lg:w-full max-lg:text-center">
			<h6 class="team-title">Олена Васильєва</h6>

			<span class="team-subtitle"> Помічник адвоката</span>

			<p class="our-team-p">
				<span class="font-semibold">Освіта:</span>
				<br />
				Олена Васильєва закінчила Національний університет «Одеська юридична академія» з відзнакою, отримавши
				кваліфікацію магістра права. Її академічні успіхи підтверджують її глибокі знання та відданість
				юридичній професії.
			</p>

			<div class="max-xl:hidden">
				<p class="our-team-p">
					<span class="font-semibold">Професійні якості:</span>
					<br />
					Олена - надзвичайно грамотний фахівець, не по роках зрілий. Її компетентність і здатність швидко
					та якісно виконувати завдання викликають захоплення. Олена завжди виконує доручення не просто
					швидко, а дуже швидко та дуже грамотно. Немає такого юридичного питання, яке їй не під силу.
				</p>

				<p class="our-team-p">
					<span class="font-semibold">Особисті якості:</span>
					<br />
					Олена відзначається сумлінністю, ввічливістю, порядністю та надійністю. Вона є незамінним членом
					команди, на якого можна покластися в будь-якій ситуації.
				</p>

				<p class="our-team-p">
					<span class="font-semibold">Чому обрати Олену:</span>
					<br />
					Незважаючи на молодий вік та те, що вона ще не адвокат, рівень знань Олени вражає. Вона демонструє
					високий професіоналізм та відповідальність у своїй роботі, що робить її важливим ресурсом для
					будь-якої юридичної фірми. Олена Васильєва - це гарантія якісної та ефективної правової допомоги.
				</p>
			</div>

			<div class="max-md:visible">
				{#if isShowInfo}
					<div transition:slide>
						<div class="flex flex-col" transition:fade>
							<p class="our-team-p">
								<span class="font-semibold">Професійні якості:</span>
								<br />
								Олена - надзвичайно грамотний фахівець, не по роках зрілий. Її компетентність і здатність
								швидко та якісно виконувати завдання викликають захоплення. Олена завжди виконує доручення
								не просто швидко, а дуже швидко та дуже грамотно. Немає такого юридичного питання, яке
								їй не під силу.
							</p>

							<p class="our-team-p">
								<span class="font-semibold">Особисті якості:</span>
								<br />
								Олена відзначається сумлінністю, ввічливістю, порядністю та надійністю. Вона є незамінним
								членом команди, на якого можна покластися в будь-якій ситуації.
							</p>

							<p class="our-team-p">
								<span class="font-semibold">Чому обрати Олену:</span>
								<br />
								Незважаючи на молодий вік та те, що вона ще не адвокат, рівень знань Олени вражає. Вона
								демонструє високий професіоналізм та відповідальність у своїй роботі, що робить її важливим
								ресурсом для будь-якої юридичної фірми. Олена Васильєва - це гарантія якісної та ефективної
								правової допомоги.
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
			<source srcset="/img/our-team-four.webp" type="image/webp" />
			<img
				class="team-img"
				loading="lazy"
				width="510"
				height="596"
				src="/img/our-team-four.jpg"
				alt="Team four"
			/>
		</picture>
	</div>
</Fade>
