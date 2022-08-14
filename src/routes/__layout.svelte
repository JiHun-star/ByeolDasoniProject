<script>
	let xm = -10;
	function navbtn() {
		if (xm == -10) {
			xm = 0;
		} else {
			xm = -10;
		}
	}
</script>

<header style="margin-left: {xm}em;">
	<div class="inline-block">
		<nav class="flex flex-col">
			<a href="/"><h2>소개</h2></a>
			<a href="/team"><h2>팀 기획</h2></a>
			<a href="/compilation"><h2>합작 기획</h2></a>
			<a href="/etc"><h2>개인 참여작</h2></a>
		</nav>
	</div>
	<button on:click={navbtn}>버튼</button>
</header>
<slot />

<style>
	header {
		position: fixed;
		top: 0;
		left: 0;
		float: left;

		transition: all 250ms ease-out;
	}
	nav {
		text-align: right;
		transition: all 0.3s;

		width: 10em;
		height: 100vh;
		background-color: #222;

		padding: 1em;
		gap: 0.5em;
	}
	button {
		margin: 0;
		padding: 0;
		display: inline-block;
	}
</style>
