<script>
	import Tooltip from '../atoms/Tooltip.svelte';

	// i didnt write this idk
	let getAge = () => {
		let birthDate = new Date('2002/12/01');
		const ageMs = Date.now() - birthDate.getTime();
		const preciseAge = (ageMs / 31536000000).toFixed(10);
		return preciseAge;
	};

	let age = getAge();
	setInterval(() => {
		age = getAge();
	}, 1000);
</script>

<section id="about" class="wrapper">
	<div class="text">
		<h2>about me</h2>
		<p>
			Hello stranger! My name is Matilde, I am natural from 
			<span>Oporto, Portugal</span>
			and I'm 
			<Tooltip tip={age}><span>{Math.floor(Number(age))}</span></Tooltip>.
			<br>I am an 
			<Tooltip tip={"🖥️"}><a href="https://sigarra.up.pt/feup/en/CUR_GERAL.CUR_VIEW?pv_curso_id=742&pv_origem=CUR&pv_ano_lectivo=2021" target="_blank" rel="noopener noreferrer">
				<span>Informatics and Computer Engineering</span>
			</a></Tooltip>
			student, currently on the 2nd year of my master's.
			After my years of studying, I find myself interested by the areas of <span>Distributed Systems</span> and <span>Computer Networks</span>. You can check out my projects and past endeavours below :)
		</p>
	</div>
</section>

<style lang="scss">
	@import '../../styles/mixins.scss';

	section {
		margin-bottom: 6rem;
		gap: 4.5rem;
		grid-template-columns: 1fr 1fr;
		align-items: center;
	}

	.text {
		position: relative;
		line-height: 1.75rem;
		align-items: center;
		display: flex;
		justify-content: center;
		flex-direction: column;
	}

	span {
		font-weight: 400;
		font-family: var(--font-two);
		font-size: 0.9rem;
		background-color: var(--elevation-one);
		border-radius: 7px;
		color: var(--accent);
		padding: 0.2rem 0.5rem 0.2rem;
		width: fit-content;
	}

	a {
		text-decoration: none;
	}

	h2 {
		display: block;
		margin-top: 1rem;
		margin-bottom: 1rem;
	}

	@media (max-width: 868px) {
		section {
			display: flex;
			flex-direction: column;
			align-items: normal;
		}

		h2 {
			display: block;
			margin-bottom: 1rem;
		}
	}
</style>
