<script>
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	//로딩화면
	let loaded = false;

	onMount(() => {
		loaded = true;
	});

	//nav버튼
	let visible = false;
	function navbtn() {
		visible = !visible;
	}

	let current = '1';
</script>

{#if !loaded}
	<div class="loading">로딩중...</div>
{/if}

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
				in:fly={{ y: -30, duration: 1000, delay: 200 }}
				out:fade><h2>팀 기획</h2></a
			>
			<a
				href="/compilation"
				class:active={current === '3'}
				on:click={() => {
					current = '3';
					navbtn();
				}}
				in:fly={{ y: -30, duration: 1000, delay: 400 }}
				out:fade><h2>합작 기획</h2></a
			>
			<a
				href="/etc"
				class:active={current === '4'}
				on:click={() => {
					current = '4';
					navbtn();
				}}
				in:fly={{ y: -30, duration: 1000, delay: 600 }}
				out:fade><h2>개인 참여작</h2></a
			>
		{/if}
	</nav>
</header>

<slot />

<style>
	@media screen and (min-width: 320px) {
		.loading {
			position: fixed;
			top: 0;
			bottom: 0;
			left: 0;
			right: 0;
			display: grid;
			place-items: center;
			background-color: #fff;
			z-index: 999;
		}

		header {
			width: 100vw;
			position: fixed;
			top: -0.3em;
			left: 0;
			z-index: 100;

			color: #fafaf9;
			text-align: center;
			background: linear-gradient(45deg, #000 0%, #1c1917 100%);
			background-color: #1c1917;
			box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.429);
		}

		nav {
			padding: 0.3em;
			gap: 0.3em;
		}

		nav a:hover {
			color: #fcd34d;
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
			color: #fcd34d;
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
			box-shadow: none;
		}
	}
</style>
