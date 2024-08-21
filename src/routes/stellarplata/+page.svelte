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

	//Svelte-Splide
	import { Splide, SplideSlide, SplideTrack } from '@splidejs/svelte-splide';
	import '@splidejs/svelte-splide/css/themes/splide-sea-green.min.css';
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
			<p>한국의 보카로/음합엔 프로듀서의 창작활동을 응원합니다!</p>
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
			<Splide
				hasTrack={false}
				aria-label="Members"
				options={{
					perPage: 1,
					type: 'loop',
					autoplay: true,
					lazyLoad: 'nearby',
					preloadPages: 1,
					arrows: false,
					pagination: false,
					resetProgress: false
				}}
			>
				<SplideTrack>
					<SplideSlide><p class="SplideSlideBox">준비중 입니다</p></SplideSlide>
					<SplideSlide><p class="SplideSlideBox">준비중 입니다</p></SplideSlide>
					<SplideSlide><p class="SplideSlideBox">준비중 입니다</p></SplideSlide>
				</SplideTrack>
				<div class="splide__progress">
					<div class="splide__progress__bar" />
				</div>
			</Splide>
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

	.link-error {
		font-size: 16px;
		text-decoration: underline;
	}

	.SplideSlideBox {
		background-color: antiquewhite;
	}

	.splide__progress {
		background: #23293f;
	}

	.splide__progress__bar {
		background: #f8dc4c;
		height: 2px;
		width: 0;
	}
</style>
