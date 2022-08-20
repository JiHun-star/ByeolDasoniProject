<script lang="ts">
	import { etcyt } from '$lib/youtube';
</script>

<svelte:head>
	<title>개인 참여작</title>
</svelte:head>

<main>
	<!-- awards history -->
	<section class="awards flex justify-evenly flex-col lg:flex-row">
		<article class="basis-1/2">
			<h1>여기는 수상 내역 넣는곳</h1>
		</article>
		<article class="basis-1/2">
			<h1>여기는 영상 넣는곳</h1>
		</article>
	</section>

	<!-- etc works -->
	<h1>기타 개인 참여작</h1>

	<section class="grid ustify-items-center grid-cols-1 md:grid-cols-3 gap-3">
		{#each etcyt as yt}
			<div class="gridbox">
				<iframe
					src="https://www.youtube.com/embed/{yt.src}"
					title={yt.name}
					frameborder="0"
					allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
				/>
				<h2 class="songname">{yt.name}</h2>
			</div>
		{/each}
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

			-ms-overflow-style: none; /* IE and Edge 스크롤바 제거 */
			scrollbar-width: none; /* Firefox 스크롤바 제거 */

			background-color: #faafaf;
			background-attachment: fixed;
			background-position: center;
			background-size: cover;
			background-repeat: no-repeat;

			text-align: center;
		}

		main::-webkit-scrollbar {
			display: none; /* Chrome 스크롤바 제거 */
		}

		section {
			margin: 0;
			padding: 0;
			text-align: center;
		}

		.awards {
			padding-top: 15vh;
			width: 100vw;
			height: 100vh;
			overflow: hidden;
		}

		h1 {
			margin: 10vh auto;
			font-size: 2em;
		}

		.gridbox iframe {
			width: 80vw;
		}

		.songname {
			margin: 1em;
			font-size: 1.1em;
		}
	}

	@media screen and (min-width: 768px) {
		h1 {
			font-size: 3em;
		}

		.gridbox iframe {
			width: 31vw;
		}
	}

	@media screen and (min-width: 1024px) {
		.songname {
			font-size: 1.5em;
		}
	}
</style>
