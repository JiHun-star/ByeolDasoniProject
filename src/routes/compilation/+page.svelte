<script>
	//reveal
	import { reveal } from 'svelte-reveal';

	import { afterUpdate } from 'svelte';
	import { each, onMount } from 'svelte/internal';
	let show = false;
	afterUpdate(() => {
		show = true;
	});

	//store
	import { compilations } from './youtube';

	//tab-active
	import { count } from '../+page';
	onMount(() => {
		count.set(3);
	});
</script>

<svelte:head>
	<title>Byeol_DasoniㅣCompilation</title>
</svelte:head>

<section class="flex flex-col w-full">
	<!-- 설명 -->
	{#if show}
		<div
			class="grid card bg-zinc-400 rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-3xl uppercase">Compilation</h1>
			<br />
			<h4>이 페이지는 별다소니가 기획 및 주최한 컴필레이션 합작을 모아두는 곳입니다.</h4>
		</div>
	{/if}
	<div class="divider" />
	<!-- 컴필레이션 합작 -->
	{#each compilations as yt}
		{#if show}
			<div
				class="grid card bg-zinc-400 rounded-box place-items-center shadow-2xl"
				use:reveal={{
					threshold: 0.0,
					delay: 300,
					duration: 500,
					transition: 'blur',
					blur: 20,
					opacity: 0.5
				}}
			>
				<!-- content here -->
				<h1 class="text-2xl">{yt.name}</h1>

				<iframe
					src="https://www.youtube.com/embed/{yt.src}"
					title="YouTube video player"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
					use:reveal={{ transition: 'fly' }}
				/>
			</div>
			<div class="divider" />
		{/if}
	{/each}
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

	iframe {
		width: 95%;
		aspect-ratio: 16/9;
		border-radius: 15px;
		background-color: #999;
		margin-top: 2rem;
	}

	@media all and (min-width: 1024px) {
		iframe {
			width: 70%;
		}
	}
</style>
