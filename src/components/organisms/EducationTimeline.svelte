<script>
	import { Timeline } from 'svelte-vertical-timeline';
	import TimeItem from './TimeItem.svelte';

	let size = 0;

	const educationSlots = [
		{
			contentTitle: 'Cambridge Assessment',
			contentDescription: 'Certificate of Proficiency in English - Council of Europe Level C2',
			oppositeContent: 'NOV. 2019',
			timelineIcon: 'fluent:certificate-20-regular',
			hyperlink: 'https://www.cambridgeenglish.org/'
		},
		{
			contentTitle: 'University of Porto',
			contentDescription:
				"Bachelor's in Informatics and Computing Engineering",
			oppositeContent: 'SEP. 2020 - JUL. 2023',
			timelineIcon: 'fluent-mdl2:education',
			hyperlink: 'https://sigarra.up.pt/feup/en/WEB_PAGE.INICIAL'
		},
		{
			contentTitle: 'University of Porto',
			contentDescription: "Master's in Informatics and Computing Engineering",
			oppositeContent: 'SEP. 2023 - PRESENT',
			timelineIcon: 'fluent-mdl2:education',
			hyperlink: 'https://sigarra.up.pt/feup/en/WEB_PAGE.INICIAL'
		},
		{
			contentTitle: 'TU Wien Informatics',
			contentDescription: 'Exchange programme ERASMUS+',
			oppositeContent: 'SEP. 2024 - FEB. 2025',
			timelineIcon: 'clarity:world-line',
			hyperlink: 'https://informatics.tuwien.ac.at/'
		}
	];
  
</script>

<svelte:window bind:innerWidth={size} />

<section id="education" class="wrapper">
	<div class="title">
		<h2>education</h2>
	</div>
	
	{#if size > 868}

	<Timeline position="alternate">
		{#each educationSlots as eduSlot, index}
			<TimeItem slot={eduSlot} lastSlot={index !== educationSlots.length - 1} desktopLayout={true}/>
		{/each}
	</Timeline>

	{:else}

	<Timeline>
		{#each educationSlots as eduSlot, index}
			<TimeItem slot={eduSlot} lastSlot={index !== educationSlots.length - 1} desktopLayout={false}/>
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