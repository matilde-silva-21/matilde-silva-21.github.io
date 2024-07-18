<script lang="ts">
	import { onMount } from 'svelte';
	import '../styles/global.scss';
	import '../styles/fonts.scss';
	import Cursor from '../components/atoms/Cursor.svelte';

	let loading = true;

	onMount(() => {
		if (document.readyState === 'complete') {
			loading = false;
		}

		const classes = document.querySelector('body')?.classList;
		const stopResizeAnimation = () => {
			let timer: any = 0;
			window.addEventListener('resize', function () {
				if (timer) {
					clearTimeout(timer);
					timer = null;
				} else {
					classes?.add('stop-transitions');
				}

				timer = setTimeout(() => {
					classes?.remove('stop-transitions');
					timer = null;
				}, 100);
			});
		};

		stopResizeAnimation();
	});
	
</script>

<svelte:head>
	<meta charset="UTF-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	<meta name="theme-color" content="#CCE2F2" />
	<title>Matilde</title>
</svelte:head>

<Cursor />
<span class:loading>
	<slot />
</span>

<style>
	.loading * {
		transition: none;
	}
</style>
