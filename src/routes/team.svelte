<script lang="ts">
	import Saos from 'saos'; //scroll animaiton

	import { byeolbada, meika } from '$lib/youtube';
</script>

<svelte:head>
	<title>팀 기획</title>
</svelte:head>

<main>
	<section>
		<Saos animation={'fade-in 3s ease-out both'}>
			<h1 class="teamName">별의 바다에 가라앉고 있어</h1>
			<p class="teamexplain">
				곡: 다삥이 / 가사: 별다소니 / 조교: 피오테오<br />일러스트: 스즈란 / 영상: 퍼플슘
				<br /><br />
				<small>
					상처를 통해 우리는 무언가를 만들어 내고,
					<br />그 모습은 마치 타오르는 별처럼 아름답습니다.
					<br />창작자인 당신에게 이 노래가 작은 위로가 되길 바라고 있습니다.
				</small>
			</p>

			<div class="flex flex-wrap flex-col lg:flex-row justify-around">
				{#each byeolbada as yt}
					<article>
						<iframe
							src="https://www.youtube.com/embed/{yt.src}"
							title={yt.name}
							frameborder="0"
							allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
							allowfullscreen
						/>
						<h2 class="songname">✨ {yt.name} ✨</h2>
					</article>
				{/each}
			</div>
		</Saos>
	</section>

	<section>
		<Saos animation={'fade-in 3s ease-out both'}>
			<h1 class="teamName">project.MEIKA</h1>
			<p class="teamexplain">
				곡: 엘디큐 / 가사: 별다소니 / 믹싱: 포지티브<br />조교·일러스트·영상: 피오테오
				<br /><br />
				<small>
					메이카 프로젝트는 메이카 히메와 메이카 미코토의 노래를 통해
					<br />버드나무, 매화, 꽈리, 용담의 꽃말을 당신에게 전합니다.
				</small>
			</p>

			<div class="flex flex-wrap flex-col lg:flex-row justify-around">
				{#each meika as yt}
					<article>
						<iframe
							src="https://www.youtube.com/embed/{yt.src}"
							title={yt.name}
							frameborder="0"
							allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
							allowfullscreen
						/>
						<h2 class="songname">🌸 {yt.name} 🌸</h2>
					</article>
				{/each}
			</div>
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

			background-image: url('../img/mbg2.png');
			background-size: cover;
			background-attachment: fixed;
			background-position: center;
			background-repeat: no-repeat;

			overflow-y: scroll;

			-ms-overflow-style: none; /* IE and Edge 스크롤바 제거 */
			scrollbar-width: none; /* Firefox 스크롤바 제거 */
		}

		main::-webkit-scrollbar {
			display: none; /* Chrome 스크롤바 제거 */
		}

		section {
			width: 100vw;
			color: #fafaf9;
		}

		article {
			margin: 2vh;
		}

		iframe {
			width: 80vw;
		}

		.teamName {
			margin-top: 20vh;
			font-size: 1.8em;
			text-align: center;
			text-shadow: 0px 0px 10px rgba(255, 255, 255, 0.907);
		}

		.teamexplain {
			margin: 1em;
			font-size: 1em;
			text-align: center;
			padding-bottom: 2em;
		}

		.songname {
			margin: 1em 0;
			font-size: 1.2em;
			text-align: center;
		}
	}

	@media screen and (min-width: 1024px) {
		main {
			background-image: url('../img/wbg2.png');
		}
		article {
			margin: 4vw;
		}

		iframe {
			width: 25vw;
		}

		.teamName {
			margin-top: 18vh;
			margin-right: 11vw;
			font-size: 3em;
			text-align: right;
		}

		.teamexplain {
			margin: 2em 11vw;
			font-size: 1.3em;
			text-align: right;
		}
	}
</style>
