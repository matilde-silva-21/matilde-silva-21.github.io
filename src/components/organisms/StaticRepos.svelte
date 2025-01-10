<script lang="ts">
	import { StarIcon } from '@indaco/svelte-iconoir/star';
	import { GitForkIcon } from '@indaco/svelte-iconoir/git-fork';
	import { OpenNewWindowIcon } from '@indaco/svelte-iconoir/open-new-window';

	const staticRepos = [
		{
			link: 'https://github.com/matilde-silva-21/matilde-silva-21.github.io',
			owner: 'matilde-silva-21',
			repo: 'matilde-silva-21.github.io',
			description: 'My personal website, made with SvelteKit',
			languageColor: 'rgb(255, 62, 0)',
			language: 'Svelte',
			stars: 0,
			forks: 0
		},
		{
			link: 'https://github.com/matilde-silva-21/SDLE_project',
			owner: 'matilde-silva-21',
			repo: 'List Llama',
			description:
				'Concurrent Shopping List made with Conflict-free Replicated Data Types (CRDT). Project for Large Scale Distributed Systems course (23/24)',
			languageColor: 'rgb(0, 173, 216)',
			language: 'Go',
			stars: 0,
			forks: 0
		},
		{
			link: 'https://github.com/matilde-silva-21/iot_agricultural_simulation',
			owner: 'matilde-silva-21',
			repo: 'IoT Agricultural Simulation',
			description:
				'An IoT architecture created with an algricultural use case in mind. All components are virtualized. Project done for Project in Computer Science course (TUWien 24/25)',
			languageColor: 'rgb(48, 105, 152)',
			language: 'Python',
			stars: 0,
			forks: 0
		},
		{
			link: 'https://github.com/matilde-silva-21/grs_project',
			owner: 'matilde-silva-21',
			repo: 'NetKing',
			description:
				'Network management system to facilitate visualization and virtualization of networks. Made for Networks and Systems Management course (23/24)',
			languageColor: 'rgb(49, 120, 198)',
			language: 'TypeScript',
			stars: 0,
			forks: 0
		}
	];
</script>

<section class="wrapper" id="projects">
	<div class="title">
		<h2><span>code</span>:projects</h2>
	</div>
	<div class="grid">
		{#each staticRepos as { link, owner, repo, description, languageColor, language, stars, forks }}
			<a href={link} target="_blank" rel="noreferrer">
				<div class="repo-card">
					<div id="top-part">
						<div class="info">
							<img src="https://github.com/{owner}.png" alt="{owner}'s profile picture" id="pfp" />
							<h6>{owner}</h6>
						</div>
						<div id="open">
							<OpenNewWindowIcon color="var(--text-secondary)" size="20px" />
						</div>
					</div>
					<div>
						<h3>{repo}</h3>
						<h6>{description}</h6>
					</div>
					<div class="info-container">
						<div class="info">
							<span class="dot" style="background-color: {languageColor}" />
							<h6>{language}</h6>
						</div>
						<div class="info">
							{#if stars}
								<StarIcon color="var(--text-secondary)" size="16px" />
								<h6>{stars}</h6>
							{/if}
						</div>
						<div class="info">
							{#if forks}
								<GitForkIcon color="var(--text-secondary)" size="16px" />
								<h6>{forks}</h6>
							{/if}
						</div>
					</div>
				</div>
			</a>
		{/each}
	</div>
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
	.repo-card {
		padding: 1rem 1.25rem;
		background-color: var(--elevation-two);
		border-radius: 8px;
		min-height: 140px;
		height: 100%;
		display: flex;
		flex-direction: column;
		gap: 0.25rem;
		transition:
			transform 0.3s var(--bezier-one),
			box-shadow 0.3s var(--bezier-one);
		justify-content: space-between;
		backdrop-filter: blur(5px);
		-webkit-backdrop-filter: blur(5px);
		background-blend-mode: overlay;
		border: 1px solid var(--elevation-four);

		&:hover {
			transform: translateY(-2px);
			box-shadow: 0px 15px 25px -10px rgba(0, 0, 0, 0.25);

			#open {
				filter: brightness(1.3);
			}
		}
	}

	@keyframes shimmer {
		0% {
			background-position: -1200px 0;
		}
		100% {
			background-position: 1200px 0;
		}
	}

	a {
		text-decoration: none;
		color: var(--text-primary);
		height: 100%;
		border-radius: 8px;
	}

	h2 {
		display: inline-block;
		margin-bottom: 1rem;
	}

	#pfp {
		border-radius: 50%;
		height: 16px;
	}

	#top-part {
		display: flex;
		justify-content: space-between;
	}

	#open {
		height: 20px;
		transition: filter 0.3s var(--bezier-one);
	}

	span {
		color: var(--accent);
	}

	.grid {
		gap: 0.8rem;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		display: grid;
		grid-template-columns: 1fr 1fr;
		margin-bottom: 3rem;
		position: relative;

		@media (max-width: 600px) {
			grid-template-columns: 1fr;
		}

		@media (max-width: 868px) {
			margin-bottom: 2rem;
		}
	}

	.dot {
		height: 11px;
		width: 11px;
		border-radius: 50%;
		display: inline-block;
	}

	.info {
		display: flex;
		gap: 0.2rem;
		align-items: center;

		&-container {
			display: flex;
			gap: 0.9rem;
		}
	}

	section {
		margin-bottom: 6rem;
		gap: 4.5rem;
		grid-template-columns: 1fr 1fr;
		align-items: center;
	}
</style>
