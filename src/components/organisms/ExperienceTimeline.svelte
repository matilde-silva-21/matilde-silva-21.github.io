<script>
	import { Timeline } from 'svelte-vertical-timeline';
	import TimeItem from './TimeItem.svelte';

	let size = 0;

	const experienceSlots = [
		{
			contentTitle: 'Armis Intelligent Transport Systems',
			contentDescription: 'Curricular Internship - Creation of a Traffic Status classification model, using Artificial Intelligence',
			oppositeContent: 'FEB. 2023 - JUL. 2023',
			timelineIcon: 'material-symbols:work-outline',
			hyperlink: 'https://www.armisgroup.com/intelligent-transport-systems/'
		},
		{
			contentTitle: 'Formula Student Driverless FEUP',
			contentDescription:
				"Research and Development of smart and automated driving systems",
			oppositeContent: 'MAY 2023 - SEP. 2023',
			timelineIcon: 'gravity-ui:plug-connection',
			hyperlink: 'https://formulastudent.fe.up.pt/en/'
		},
		{
			contentTitle: 'Sky Portugal',
			contentDescription: "Summer Internship - iOS Apprentice Developer",
			oppositeContent: 'JUL. 2024 - AUG. 2024',
			timelineIcon: 'material-symbols:work-outline',
			hyperlink: 'https://www.sky.com/'
		},
		{
			contentTitle: 'Computer Graphics and Multimedia Nucleus',
			contentDescription: 'Game Development and organization of multimedia events',
			oppositeContent: 'SEP. 2023 - PRESENT',
			timelineIcon: 'gravity-ui:plug-connection',
			hyperlink: 'https://ncgm.fe.up.pt/en/home'
		}
	];
  
</script>

<svelte:window bind:innerWidth={size} />

<section id="experience" class="wrapper">
	<div class="title">
		<h2>experience</h2>
	</div>
	
	{#if size > 868}

	<Timeline position="alternate">
		{#each experienceSlots as expSlot, index}
			<TimeItem slot={expSlot} lastSlot={index !== experienceSlots.length - 1} desktopLayout={true}/>
		{/each}
	</Timeline>

	{:else}

	<Timeline>
		{#each experienceSlots as expSlot, index}
			<TimeItem slot={expSlot} lastSlot={index !== experienceSlots.length - 1} desktopLayout={false}/>
		{/each}
	</Timeline>
	
	{/if}

</section>

<style lang="scss">
	@import '../../styles/mixins.scss';

	.title {
		display: flex;
		justify-content: center;
		margin-top: 0;

		@media (max-width: 868px) {
			justify-content: left;
		}
	}

	h2 {
		display: inline-block;
		margin-bottom: 1rem;
	}

	section {
		margin-bottom: 4.75rem;
		gap: 4.5rem;
		grid-template-columns: 1fr 1fr;
		align-items: center;
	}
	
</style>