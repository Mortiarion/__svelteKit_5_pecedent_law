<script lang="ts">
	import TeamOne from './components/TeamOne.svelte';
	import TeamTwo from './components/TeamTwo.svelte';
	import TeamThree from './components/TeamThree.svelte';
	import TeamFour from './components/TeamFour.svelte';
	import TeamFive from './components/TeamFive.svelte';
	import TeamSix from './components/TeamSix.svelte';

	type TTeamInfo = {
		teamOne: boolean;
		teamTwo: boolean;
		teamThree: boolean;
		teamFour: boolean;
		teamFive: boolean;
		teamSix: boolean;
	};

	let isShowInfo: TTeamInfo = {
		teamOne: false,
		teamTwo: false,
		teamThree: false,
		teamFour: false,
		teamFive: false,
		teamSix: false
	};

	function toggleInfo(team: keyof TTeamInfo) {
		isShowInfo[team] = !isShowInfo[team];
	}
</script>

<section id="our-teame" class="py-24">
	<div class="container">
		<h3 class="main-title">Наша команда</h3>

		<hr class="color-cccccc my-10" />

		<TeamOne toggleInfo={() => toggleInfo('teamOne')} isShowInfo={isShowInfo.teamOne} />

		<hr class="color-cccccc my-10" />

		<TeamTwo toggleInfo={() => toggleInfo('teamTwo')} isShowInfo={isShowInfo.teamTwo} />

		<hr class="color-cccccc my-10" />

		<TeamThree toggleInfo={() => toggleInfo('teamThree')} isShowInfo={isShowInfo.teamThree} />

		<hr class="color-cccccc my-10" />

		<TeamFour toggleInfo={() => toggleInfo('teamFour')} isShowInfo={isShowInfo.teamFour} />

		<hr class="color-cccccc my-10" />

		<TeamFive toggleInfo={() => toggleInfo('teamFive')} isShowInfo={isShowInfo.teamFive} />

		<hr class="color-cccccc my-10" />

		<TeamSix toggleInfo={() => toggleInfo('teamSix')} isShowInfo={isShowInfo.teamSix} />

		<hr class="color-cccccc my-10" />
	</div>
</section>
