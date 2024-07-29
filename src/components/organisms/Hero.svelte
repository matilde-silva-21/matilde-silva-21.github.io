<script>
	import HeroImage from '../../components/atoms/HeroImage.svelte';
	import Button from '../atoms/Button.svelte';
	import Socials from '../molecules/Socials.svelte';

	function handleClick() {
		// TODO uncomment this when CV is ready
		//window.open(`/curriculum_vitae.html`, "_blank");
		window.open(`/cv.html`, "_blank");
	}
</script>

<section id="home" class="wrapper">
	<div>
		<h1>matilde silva</h1>
		<h4>0.5x programmer</h4>
		<div class="socials">
			<Socials />
		</div>
		<Button side on:click={handleClick} on:keypress={handleClick}>Check out my CV ↗</Button>
	</div>
	<HeroImage />
</section>

<style lang="scss">
	@import '../../styles/mixins.scss';

	section {
		scroll-margin-top: 20rem;
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 5.75rem;
		margin-top: 7rem;

		@media screen and (max-width: 868px) {
			margin-top: 4rem;
		}

		@media screen and (max-width: 768px) {
			margin-bottom: 2.75rem;
		}

		@media screen and (max-width: 500px) {
			display: block;
		}
	}

	.socials {
		margin-top: 1rem;
		margin-bottom: 1.7rem;
	}

	h4 {
		margin-top: 1rem;
	}

	@media screen and (max-width: 1240px) {
		h1 {
			min-height: 0vw;
			font-size: clamp(4rem, 10vw, 6.25rem);
		}

		h4 {
			min-height: 0vw;
			font-size: clamp(1.4rem, 2.4vw, 1.5rem);
		}
	}

</style>
