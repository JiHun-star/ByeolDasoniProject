<script>
	import { fade, fly } from 'svelte/transition';

	let visible = false;
	function navbtn() {
		visible = !visible;
	}

	let current = '1';
</script>

<header>
	<nav class="flex flex-col">
		<button class="open" on:click={navbtn}>M E N U</button>
		{#if visible}
			<a
				href="/"
				class:active={current === '1'}
				on:click={() => {
					current = '1';
					navbtn();
				}}
				in:fly={{ y: -30, duration: 1000 }}
				out:fade><h2>소개</h2></a
			>
			<a
				href="/team"
				class:active={current === '2'}
				on:click={() => {
					current = '2';
					navbtn();
				}}
				in:fly={{ y: -30, duration: 1300 }}
				out:fade><h2>팀 기획</h2></a
			>
			<a
				href="/compilation"
				class:active={current === '3'}
				on:click={() => {
					current = '3';
					navbtn();
				}}
				in:fly={{ y: -30, duration: 1600 }}
				out:fade><h2>합작 기획</h2></a
			>
			<a
				href="/etc"
				class:active={current === '4'}
				on:click={() => {
					current = '4';
					navbtn();
				}}
				in:fly={{ y: -30, duration: 1900 }}
				out:fade><h2>개인 참여작</h2></a
			>
		{/if}
	</nav>
</header>
<slot />

<style>
	@media screen and (min-width: 320px) {
		header {
			width: 100vw;
			position: fixed;
			top: -0.3em;
			left: 0;
			z-index: 100;

			color: #fafaf9;
			text-align: center;

			background-color: #1c1917;
		}
		nav {
			padding: 0.3em;
			gap: 0.3em;
		}

		nav a:hover {
			color: #fbbf24;
			transition: all 800ms ease;
		}

		.open {
			margin: 10px;
			padding: 0.3em 0;

			border-bottom: 0.1em solid #fafaf9;

			font-family: 'GyeonggiTitleM';
			font-size: 1.4em;

			transition: all 250ms ease;
		}

		.open:hover {
			letter-spacing: 0.3em;
		}

		.active {
			color: #fbbf24;
		}
	}

	@media screen and (min-width: 768px) {
		header {
			top: -0.5em;
		}
		nav {
			padding: 1em;
			gap: 0.5em;
		}
	}

	@media screen and (min-width: 1024px) {
		header {
			width: 15em;
			background: none;
		}
	}
</style>
