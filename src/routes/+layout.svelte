<script>
	import './styles.css';

	//tab-active
	import { count } from './+page';
	let tabActive = 0;
	const active = count.subscribe((value) => {
		tabActive = value;
	});
</script>

<div class="app" id="app">
	<header>
		<nav role="tablist" class="tabs tabs-bordered">
			<a href="/" role="tab" class="tab" class:tab-active={tabActive === 1}>Portfolio</a>
			<a href="/team" role="tab" class="tab" class:tab-active={tabActive === 2}>Team</a>
			<a href="/compilation" role="tab" class="tab" class:tab-active={tabActive === 3}>
				Compilation
			</a>
			<a href="/stellarplata" role="tab" class="tab" class:tab-active={tabActive === 4}>
				StellarPlata
			</a>
		</nav>
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
		padding: 8vh 0 0;
	}

	nav {
		display: block;
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

	footer {
		padding-bottom: 8vh;
	}
</style>
