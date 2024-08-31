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
			<br />
			<article>
				<ul>
					<li class="text-xl">
						Stellar Pick ! : 한국 보카로 신곡 중에서 엄선하여 추천해 드립니다.
					</li>
					<li class="text-xl">
						Shout-out STAR ★ : 5곡으로 한국 보카로 프로듀서 분들을 소개합니다.
					</li>
				</ul>
			</article>
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

	li {
		margin: 0 10px;
	}

	@media all and (min-width: 1024px) {
		iframe {
			width: 70%;
		}
	}
</style>
