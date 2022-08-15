<script>
	import '../app.css'; //tailwindcss
	import '@fortawesome/fontawesome-free/js/all.min.js'; //fontawesome
</script>

<svelte:head>
	<title>Byeol Dasoni's projects : 별다소니의 기획 및 작사 소개</title>
</svelte:head>

<section>
	<h1>별다소니</h1>
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
	<p class="textbox">
		이해하기 쉬운 단어로,
		<br /><br />선율에 담긴 감정과 어우러지면서,
		<br /><br />시적인 아름다움을 담아내는,
		<br /><br />그런 가사를 써내려가고자 노력하고 있습니다.
		<br /><br /><small>*협업 요청은 SNS의 DM으로 보내주세요.</small>
	</p>
</section>

<style>
	@media screen and (min-width: 320px) {
		section {
			height: 100vh;
			padding-top: 8em;

			background-image: url('bg.jpg');
			background-size: cover;
			background-attachment: fixed;

			text-align: center;
			color: #fafaf9;
		}

		aside {
			margin-top: 0.5em;
			padding: 10px 33px;
			display: inline-block;

			border-radius: 12px;
			background-color: #fafaf9;
			color: #1c1917;
			font-size: 1.5em;
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
			padding-top: 8em;
		}
	}

	@media screen and (min-width: 1024px) {
		section {
			padding-top: 20em;
			padding-right: 10em;
			text-align: right;
		}

		aside {
			margin-top: 0;
			padding: 5px 22px;
		}
	}
</style>
