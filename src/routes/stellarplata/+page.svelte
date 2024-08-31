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
			<!-- title -->
			<picture>
				<img
					src="/images/spheader.png"
					alt="스텔라 플라타 헤더"
					class="headImg"
					use:reveal={{ transition: 'fly' }}
				/>
			</picture>
			<br /><br />
			<p>'StellarPlata (스텔라플라타)'는</p>
			<br />
			<p>한국의 보카로 (음합엔) 프로듀서의 창작활동을 응원합니다!</p>
			<br /><br />
			<a
				href="https://www.youtube.com/@StellarPlata?sub_confirmation=1"
				rel="noreferrer"
				target="_blank"
				class="link-error"
				><i class="fa-brands fa-youtube" />
				<b>&nbsp;유튜브 채널 바로가기</b>
			</a>
			<br /><br /><br /><br /><br />

			<!-- diff -->
			<div class="diff aspect-[16/9]">
				<div class="diff-item-1">
					<div class="grid place-content-center">
						<h1 class="diffh1">Shout-out STAR ★</h1>
						<small class="diffsmall">
							다섯 곡으로<br />한국 보카로 프로듀서를 소개합니다.
						</small>
					</div>
				</div>
				<div class="diff-item-2">
					<div class="grid place-content-center">
						<h1 class="diffh1">Stellar Pick !</h1>
						<small class="diffsmall">
							한국 보카로 신곡을<br />스텔라플라타에서 엄선하여 소개합니다.
						</small>
					</div>
				</div>
				<div class="diff-resizer" />
			</div>
			<br /><br /><br /><br /><br />

			<!-- album -->
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

	.headImg {
		margin: 0 auto;
		width: 95%;
	}

	.link-error {
		font-size: 16px;
		text-decoration: underline;
	}

	.diff {
		background-color: #f8dc4c;
	}

	.diff-item-2 {
		background-color: #23293f;
		color: #fff;
	}

	.diff-item-1 {
		color: #23293f;
	}

	.diffh1 {
		font-size: 4vw;
	}
</style>
