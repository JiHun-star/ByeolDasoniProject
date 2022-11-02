<script>
	import './styles.css';
</script>

<div class="app" id="app">
	<header>
		<h1 class="bgTitle">
			<br />
			저기 밤하늘에 수많은 별이 타오르고 있습니다. 오롯이 홀로 고독하게 상처를 안고 있는 그 생명의 빛이
			모여, 세상은 잠기고 적막만이 남았습니다. 그 모습이 어찌나 아름답게 위태롭고, 애타게 달콤하고, 차갑고
			뜨거운 것인지 알게 된 순간. 눈가에 밀려드는 수평선 그 위로 새벽이 벅차오르고 있었습니다. 저는 당신을
			사랑하고 싶습니다.
		</h1>
	</header>

	<main>
		<slot />
	</main>

	<div class="topBtn">
		<a href="#app" class="hover:text-primary active:text-primary-focus">
			<i class="fa-solid fa-square-caret-up fa-3x" />
		</a>
	</div>

	<footer>
		<p>Copyright <i class="fa-regular fa-copyright" /> 2022 by Byeol Dasoni.</p>
	</footer>
</div>

<style>
	header {
		position: fixed;
		top: 0;
		left: 50%;
		transform: translateX(-50%);
		opacity: 0.3;
	}

	.bgTitle {
		font-size: 2.6vw;
	}

	.app {
		margin: 0 auto;
		width: 82vw;
		text-align: center;
	}

	.topBtn {
		position: fixed;
		bottom: 10px;
		right: 20px;
	}
</style>
