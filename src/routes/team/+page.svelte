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
	import { winterflower, byeolbada, meika } from './youtube';

	//tab-active
	import { count } from '../+page';
	onMount(() => {
		count.set(2);
	});
</script>

<svelte:head>
	<title>Byeol_DasoniㅣCompilation</title>
</svelte:head>

<section class="flex flex-col w-full">
	<!-- 설명 -->
	{#if show}
		<div
			class="grid card bg-secondary-content rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-3xl text-info-content uppercase">Team</h1>
			<br />
			<h4>이 페이지는 별다소니가 기획한 팀 프로젝트 작업물을 모아두는 곳입니다.</h4>
		</div>
	{/if}
	<div class="divider" />
	<!-- 팀 프로젝트 -->
	<!-- 겨울이 있던 꽃 -->
	{#if show}
		<div
			class="grid card bg-secondary-content rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-2xl text-info-content">겨울이 있던 꽃</h1>
			<br />
			{#each winterflower as yt}
				<!-- content here -->
				<iframe
					src="https://www.youtube.com/embed/{yt.src}"
					title="YouTube video player"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
					use:reveal={{ transition: 'fly' }}
				/>
				<br />
				<h2>〈 {yt.name} 〉</h2>
				<a href={yt.linked} target="_blank" title="음원 스트리밍 들으러가기"
					><i class="fa-solid fa-music" /></a
				>
			{/each}
		</div>
	{/if}
	<div class="divider" />
	<!-- 별의 바다에 가라앉고 있어 -->
	{#if show}
		<div
			class="grid card bg-secondary-content rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-2xl text-info-content">별의 바다에 가라앉고 있어</h1>
			<br />
			{#each byeolbada as yt}
				<!-- content here -->
				<iframe
					src="https://www.youtube.com/embed/{yt.src}"
					title="YouTube video player"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
					use:reveal={{ transition: 'fly' }}
				/>
				<br />
				<h2>〈 {yt.name} 〉</h2>
			{/each}
		</div>
	{/if}
	<div class="divider" />
	<!-- 메이카 프로젝트 -->
	{#if show}
		<div
			class="grid card bg-secondary-content rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-2xl text-info-content">메이카 프로젝트</h1>
			<br />
			{#each meika as yt}
				<!-- content here -->
				<iframe
					src="https://www.youtube.com/embed/{yt.src}"
					title="YouTube video player"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
					use:reveal={{ transition: 'fly' }}
				/>
				<br />
				<h2>〈 {yt.name} 〉</h2>
			{/each}
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
