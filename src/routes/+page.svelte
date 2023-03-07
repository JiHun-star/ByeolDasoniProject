<script>
	//reveal
	import { reveal } from 'svelte-reveal';
	import { copy } from 'svelte-copy';

	import { afterUpdate } from 'svelte';
	import { each, onMount } from 'svelte/internal';
	let show = false;
	afterUpdate(() => {
		show = true;
	});

	//store
	import { byeolbada, meika, etcyt } from './youtube';

	//toggle
	let toggleshow1 = true;
	let toggleshow2 = false;
	let toggleshow3 = false;
	let toggleshow4 = false;

	//tab-active
	import { count } from './+page';
	onMount(() => {
		count.set(1);
	});
</script>

<svelte:head>
	<title>Byeol_Dasoni</title>
</svelte:head>

<section class="flex flex-col w-full">
	<!-- profile -->
	{#if show}
		<div
			class="grid card bg-neutral-content rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 100,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<div class="flex items-center gap-6 flex-col xl:flex-row xl:items-start">
				<picture>
					<img src="/images/profile.png" alt="프로필 사진" class="profileImg" />
				</picture>
				<div class="text-center xl:text-left">
					<h1 class="text-3xl text-info-content">별다소니</h1>
					<h2 class="text-xl">서브컬쳐 작사가</h2>
					<ul class="flex flex-row gap-4 justify-center xl:justify-start">
						<li>
							<a href="mailto:rlarkspx@gmail.com" rel="noreferrer" target="_blank">
								<i class="fa-solid fa-envelope text-2xl" />
							</a>
						</li>
						<li>
							<a href="https://www.youtube.com/@BDSN_Official" rel="noreferrer" target="_blank">
								<i class="fa-brands fa-youtube text-2xl" />
							</a>
						</li>
						<li>
							<a href="https://twitter.com/rlarkspx" rel="noreferrer" target="_blank">
								<i class="fa-brands fa-twitter text-2xl" />
							</a>
						</li>
						<li>
							<button
								use:copy={`별다소니#6174`}
								on:svelte-copy={(event) => alert('Copied : ' + event.detail)}
								on:svelte-copy:error={(event) =>
									alert(`There was an error: ${event.detail.message}`)}
							>
								<i class="fa-brands fa-discord text-2xl" />
							</button>
						</li>
					</ul>
					<br />
					<p>
						마음 깊은 곳에 남겨져 있는 상처와 소망 그리고 이야기를 오선지 위에서 전해지는 감정과
						어우러지도록 가사로 써내려가는 일을 합니다.
					</p>
					<br />
					<p>
						주로 보컬로이드/음성합성엔진 음악 쪽에서 활동하고 있습니다.
						<br />작사 의뢰는 트위터 or 디스코드 DM, 혹은 이메일을 이용해 주세요!
						<br />
						<br />❕VO!CE채널 운영중.<br />
						<br />❄️'겨울이 있던 꽃' 팀장
						<br />✨'별의 바다에 가라앉고 있어' 팀장 (활동 종료)<br />
						<br />📞"Phone Booth" Digital Single Album 참여
						<br />🎉"Hello, space!-UNI 5th Anniversary Album-" 참여
						<br />🎉"Re:Birth-SeeU 10th Anniversary Album-" 참여
						<br />🎺"첫 만남(初めての出会い)" CD Album 참여
					</p>
				</div>
			</div>
		</div>
	{/if}
	<div class="divider" />
	<!-- awords -->
	{#if show}
		<div
			class="grid card bg-accent-content rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-2xl text-info-content">수상경력</h1>
			<br />
			<h2 class="text-xl">새로운 경기도 노래 공정한 공모전<br />🏆작사부문 대상🏆</h2>
			<br />
			<input type="checkbox" class="toggle toggle-neutral" bind:checked={toggleshow1} />
			{#if toggleshow1}
				<iframe
					src="https://www.youtube.com/embed/eGmztNGkBOo"
					title="YouTube video player"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
					use:reveal={{ transition: 'fly' }}
				/>
				<iframe
					src="https://www.youtube.com/embed/PvuZNBbuN4g"
					title="YouTube video player"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
					use:reveal={{ transition: 'fly' }}
				/>
				<iframe
					src="https://www.youtube.com/embed/uEdxNzsdwZE"
					title="YouTube video player"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
					use:reveal={{ transition: 'fly' }}
				/>
			{/if}
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
			<input type="checkbox" class="toggle toggle-neutral" bind:checked={toggleshow2} />
			{#if toggleshow2}
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
			{/if}
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
			<input type="checkbox" class="toggle toggle-neutral" bind:checked={toggleshow3} />
			{#if toggleshow3}
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
			{/if}
		</div>
	{/if}
	<div class="divider" />
	<!-- 기타 작업물 -->
	{#if show}
		<div
			class="grid card bg-warning rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-2xl text-info-content">기타 참여작 <small>(최신순)</small></h1>
			<br />
			<input type="checkbox" class="toggle toggle-neutral" bind:checked={toggleshow4} />
			<br />
			{#if toggleshow4}
				{#each etcyt as yt}
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
			{/if}
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

	.profileImg {
		width: 180px;
		border-radius: 15%;
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
