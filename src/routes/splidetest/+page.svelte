<script>
	//splide
	import { Splide, SplideSlide, SplideTrack } from '@splidejs/svelte-splide';
	import '@splidejs/svelte-splide/css/skyblue';

	const options = {
		type: 'loop',
		perPage: 1,
		autoplay: true,
		direction: 'ttb',
		height: '60vh',
		wheel: true,
		lazyLoad: 'nearby',
		breakpoints: {
			height: '6rem'
		}
	};
</script>

<svelte:head>
	<title>Byeol_Dasoniㅣtest</title>
</svelte:head>

<div class="wrapper">
	<h2 id="autoplay-example-heading">Autoplay</h2>

	<Splide {options} hasTrack={false} aria-labelledby="autoplay-example-heading">
		<div style="position: relative">
			<SplideTrack>
				<SplideSlide>
					<img src="/profile/1.png" alt="1" />
				</SplideSlide>
				<SplideSlide>
					<img src="/profile/2.png" alt="2" />
				</SplideSlide>
			</SplideTrack>
		</div>

		<div class="splide__progress">
			<div class="splide__progress__bar" />
		</div>
	</Splide>
</div>

<style>
	.wrapper {
		display: block;
		margin: 10vh auto;
	}

	img {
		height: 60vh;
		margin: 0 auto;
		padding: 5rem;
	}
</style>
