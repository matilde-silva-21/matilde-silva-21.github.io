<script>
	import Social from '../atoms/Social.svelte';
	import { GitHubIcon } from '@indaco/svelte-iconoir/github';
	import { MailIcon } from '@indaco/svelte-iconoir/mail';
	import Icon from '@iconify/svelte';
	
</script>

<div class="socials-container">
	<Social tip="matilde-silva-21" link="https://github.com/matilde-silva-21">
		<GitHubIcon color="var(--accent)" />
	</Social>

	<Social tip="matilde.m.silva.21@gmail.com" link="mailto:matilde.m.silva.21@gmail.com">
		<MailIcon color="var(--accent)" />
	</Social>

	<Social tip="matilde-m-silva" link="https://www.linkedin.com/in/matilde-m-silva/">
		<Icon icon="uil:linkedin" color="var(--accent)" font-size="28px"/>
	</Social>
</div>

<style>
	.socials-container {
		display: flex;
		gap: 0.75rem;
	}
</style>
