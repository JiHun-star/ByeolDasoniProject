<script>
</script>

<svelte:head>
	<title>팀 기획</title>
</svelte:head>
<main>
	<section>1</section>
	<section>2</section>
	<section>3</section>
	<section>4</section>
</main>

<style>
	@media screen and (min-width: 320px) {
		/* 부모 App */
		main {
			scroll-snap-type: y mandatory;
			overflow-y: scroll;
			-ms-overflow-style: none; /* IE and Edge 스크롤바 제거 */
			scrollbar-width: none; /* Firefox 스크롤바 제거 */
		}

		main::-webkit-scrollbar {
			display: none; /* Chrome 스크롤바 제거 */
		}

		/* 자식 section들 */
		section {
			display: flex;
			justify-content: center;
			align-items: center;
			width: 100vw;
			height: 100vh;
			scroll-snap-align: start;
			color: #fff;
			font-size: 3rem;
			font-weight: bold;
		}

		/* 홀수번째 자식 */
		section:nth-child(odd) {
			background-color: cadetblue;
		}

		/* 짝수번째 자식 */
		section:nth-child(even) {
			background-color: lightcoral;
		}
	}

	@media screen and (min-width: 768px) {
	}

	@media screen and (min-width: 1024px) {
	}
</style>
