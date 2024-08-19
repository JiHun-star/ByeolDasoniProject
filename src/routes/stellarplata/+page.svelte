<script>
	//reveal
	import { reveal } from 'svelte-reveal';

	import { afterUpdate } from 'svelte';
	import { each, onMount } from 'svelte/internal';
	let show = false;
	afterUpdate(() => {
		show = true;
	});

	//tab-active
	import { count } from '../+page';
	onMount(() => {
		count.set(4);
	});
</script>

<svelte:head>
	<title>Byeol_DasoniㅣStellarPlata</title>
</svelte:head>

<section>
	{#if show}
		<div
			class="grid card rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<picture>
				<img
					src="/images/spheader.png"
					alt="스텔라 플라타 헤더"
					class="headImg"
					use:reveal={{ transition: 'fly' }}
				/>
			</picture>
		</div>
	{/if}
</section>

<style>
	section {
		padding: 8vh 0;
	}

	.card {
		width: 80vw;
		padding: 50px 40px;
		margin: 0 auto;
	}
</style>
