<svelte:head>
	<title>Byeol Dasoni's projects : 별다소니의 기획 및 작사 소개</title>
</svelte:head>

<section>
	<h1>별다소니</h1>

	<!-- sns -->
	<aside>
		<a
			href="https://www.youtube.com/channel/UCDn4683YUTBdzSVRRrpZLYQ"
			target="_blank"
			title="유튜브"
		>
			<i class="fa-brands fa-youtube" />
		</a>
		<a href="https://twitter.com/rlarkspx" target="_blank" title="트위터">
			<i class="fa-brands fa-twitter" />
		</a>
		<a href="https://www.instagram.com/byeoldasoni2/" target="_blank" title="인스타그램">
			<i class="fa-brands fa-instagram" />
		</a>
	</aside>

	<!-- text -->
	<p class="textbox">
		이해하기 쉬운 단어로
		<br /><br />선율에 담긴 감정을 건져내어서
		<br /><br />한 편의 고백처럼 아름다운 방식으로
		<br /><br />가사를 써내려가고자 노력하고 있습니다
		<br /><br /><small>*협업 요청은 SNS의 DM으로 보내주세요</small>
	</p>
</section>

<style>
	@media screen and (min-width: 320px) {
		h1 {
			text-shadow: 0px 0px 10px rgba(255, 255, 255, 0.907);
		}

		section {
			height: 100vh;
			padding-top: 15vh;

			background-image: url('../img/mbg.png');
			background-size: cover;
			background-attachment: fixed;
			background-position: center;
			background-repeat: no-repeat;

			text-align: center;
			color: #fafaf9;

			overflow: scroll;
			-ms-overflow-style: none; /* IE and Edge 스크롤바 제거 */
			scrollbar-width: none; /* Firefox 스크롤바 제거 */
		}

		section::-webkit-scrollbar {
			display: none; /* Chrome 스크롤바 제거 */
		}

		aside {
			margin-top: 2em;
			padding: 10px 33px;
			display: inline-block;

			border-radius: 12px;
			background-color: #fafaf9e4;
			color: #1c1917;
			font-size: 1.3em;
		}

		aside a {
			padding: 10px;
		}

		.textbox {
			padding-top: 3em;
		}
	}

	@media screen and (min-width: 768px) {
		section {
			padding-top: 20vh;
		}
	}

	@media screen and (min-width: 1024px) {
		section {
			padding-top: 35vh;
			padding-right: 10vw;
			text-align: right;
			background-image: url('../img/wbg.png');
		}

		aside {
			margin-top: 0;
			padding: 5px 22px;
		}
	}
</style>
