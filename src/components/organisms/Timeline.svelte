<script>
import {
	Timeline,
	TimelineItem,
	TimelineSeparator,
	TimelineDot,
	TimelineConnector,
	TimelineContent,
	TimelineOppositeContent
} from 'svelte-vertical-timeline';

const options = [
	{ title: 'Eat', time: '09:30 am' },
	{ title: 'Sleep', time: '10:00 am' },
	{ title: 'Code', time: '11:00 am' },
	{ title: 'Eat', time: '01:00 pm' },
	{ title: 'Eat', time: '09:30 am' },
	{ title: 'Sleep', time: '10:00 am' },
	{ title: 'Code', time: '11:00 am' },
	{ title: 'Eat', time: '01:00 pm' },
	{ title: 'Eat', time: '09:30 am' },
	{ title: 'Sleep', time: '10:00 am' },
	{ title: 'Code', time: '11:00 am' },
	{ title: 'Eat', time: '01:00 pm' }
];
</script>

<section id="experience" class="wrapper">
	<div class="title">
		<h2>experience</h2>
	</div>
	<Timeline position="alternate">
	{#each options as option}
		<TimelineItem>
			<TimelineOppositeContent slot="opposite-content">
				<p>{option.time}</p>
			</TimelineOppositeContent>
			<TimelineSeparator>
				<TimelineDot style={'background-color: #7CD5E2;'}/>
				<TimelineConnector />
			</TimelineSeparator>
			<TimelineContent>
				<h3>{option.title}</h3>
			</TimelineContent>
		</TimelineItem>
	{/each}
	</Timeline>
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
	
</style>