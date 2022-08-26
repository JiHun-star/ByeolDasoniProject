<script lang="ts">
	import Saos from 'saos'; //scroll animaiton
	import Carousel from '../components/carousel.svelte';
	import { byeoljari, dongyang } from '$lib/youtube';
</script>

<svelte:head>
	<title>합작 기획</title>
</svelte:head>

<main>
	<!-- 겨울 별자리 합작 -->
	<section class="backdrop-saturate-0">
		<Saos animation={'fade-in 4s ease-out both'} once>
			<h1 class="cotitle">겨울 별자리 합작</h1>
			<Carousel images={byeoljari} />
			<p class="cotext block lg:hidden">
				<br /><br />추운 겨울철 밤하늘을 올려다보면,
				<br /><br />눈동자 한가득 담기는 천체의 아름다움과
				<br /><br />떠오르는 추억과 이야기를 노래에 담아봅니다.
			</p>
		</Saos>
	</section>

	<!-- 시유 동양풍 합작 -->
	<section class="backdrop-hue-rotate-30">
		<Saos animation={'fade-in 4s ease-out both'} once>
			<h1 class="cotitle">시유 동양풍 합작</h1>
			<Carousel images={dongyang} />
			<p class="cotext block lg:hidden">
				<br /><br />시유의 9번째 생일을 맞이하여
				<br /><br />우리나라 전통의 아름다움을 담아낸 노래로
				<br /><br />자랑스러운 한국 보컬로이드인
				<br /><br />시유를 널리 이롭게 합니다.
			</p>
		</Saos>
	</section>
</main>

<style>
	@media screen and (min-width: 320px) {
		main {
			margin: 0;
			padding: 0;

			width: 100vw;
			height: 100vh;

			overflow-y: scroll;
			scroll-snap-type: y mandatory;

			-ms-overflow-style: none; /* IE and Edge 스크롤바 제거 */
			scrollbar-width: none; /* Firefox 스크롤바 제거 */

			background-image: url(../img/bg3.png);
			background-attachment: fixed;
			background-position: center;
			background-size: cover;
			background-repeat: no-repeat;
		}

		main::-webkit-scrollbar {
			display: none; /* Chrome 스크롤바 제거 */
		}

		section {
			margin: 0;
			padding: 0;

			width: 100vw;
			height: 100vh;

			scroll-snap-align: start;
		}

		.cotitle {
			padding-top: 22vh;
			padding-bottom: 1em;
			font-size: 2em;
			text-align: center;
			color: #fafaf9;
			text-shadow: 0px 0px 10px rgba(255, 255, 255, 0.907);
		}

		.cotext {
			padding-top: 1em;
			text-align: center;
			color: #fafaf9;
			font-size: 1em;
		}
	}
	@media screen and (min-width: 1024px) {
		.cotitle {
			padding-top: 10vh;
			padding-bottom: 1em;
			font-size: 3em;
		}
	}
</style>
