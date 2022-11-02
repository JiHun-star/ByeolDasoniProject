<script>
	import './styles.css';
</script>

<div class="app" id="app">
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
