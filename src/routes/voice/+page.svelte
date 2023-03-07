<script>
	//reveal
	import { reveal } from 'svelte-reveal';

	import { afterUpdate } from 'svelte';
	import { each, onMount } from 'svelte/internal';
	let show = false;
	afterUpdate(() => {
		show = true;
	});

	//store
	import { producers } from './producer';

	//tab-active
	import { count } from '../+page';
	onMount(() => {
		count.set(2);
	});
</script>

<svelte:head>
	<title>Byeol_DasoniㅣVO!CE</title>
</svelte:head>

<section class="flex flex-col w-full">
	<!-- monthly video -->
	{#if show}
		<div
			class="grid card bg-neutral rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-4xl text-neutral-content">VO!CE CHART</h1>
			<br />
			<h1 class="text-3xl text-neutral-content">- 2023.02 -</h1>
			<iframe
				src="https://www.youtube.com/embed/OZuSJqJquGw"
				title="YouTube video player"
				frameborder="0"
				allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
				allowfullscreen
				use:reveal={{ transition: 'fly' }}
			/><br />
			<h5 class="py-4 text-error">
				<i class="fa-brands fa-youtube" />
				<b>
					<a
						class="link link-hover"
						rel="noreferrer"
						href="https://www.youtube.com/channel/UCZQvu2SAjwJypMEQoHLLYOA"
						target="_blank"
					>
						YouTube Channel 바로가기
					</a>
				</b>
			</h5>
		</div>
	{/if}
	<div class="divider" />
	<!-- introduce -->
	{#if show}
		<div
			class="grid card bg-base-200 rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-3xl text-base-content">WHAT is VO!CE ?</h1>
			<br />
			<h4 class="text-base-content">
				보컬 캐릭터(보컬로이드) 및 음성합성엔진을 이용하시는
				<br />한국의 서브컬쳐 음악 프로듀서 분들의 홍보를 미약하게나마 돕고자 만들어진 채널입니다.
				<br /><br />VO!CE에 가입된 유튜브 채널을 구독하여, 투고된 오리지널 곡들을 수집하고
				<br />매월 신곡들을 소개하는 영상을 올리고 있습니다.
				<br /><br />개개인의 실력을 따지지 않고 자유롭게 가입 신청을 받고 있으니,
				<br />가입을 원하시는 분들은 아래 구글폼을 작성해 주시면 감사하겠습니다.
				<br /><br />
				<a
					rel="noreferrer"
					href="https://forms.gle/rMMs65QyF4GynqnC8"
					target="_blank"
					class="link link-primary"
				>
					<i class="fa-solid fa-pen-to-square" /> 한국 보카로P 신곡 소개 VO!CE 가입 신청서
				</a>
			</h4>
		</div>
	{/if}
	<div class="divider" />
	{#if show}
		<div
			class="grid card bg-base-200 rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-3xl text-base-content">VO!CE 가입시 참고사항</h1>
			<br />
			<h4 class="text-base-content">
				신청서 제출 시, VO!CE에서 여러분의 채널을 구독하며,
				<br />매월 여러분의 유튜브 채널에 업로드된 영상을 분석하여 월간 'VO!CE CHART' 영상 리스트에
				올립니다.
				<br /><br />(반드시 창작자 본인이 신청해주세요!)
				<br /><br />신청서 제출 시, 영상 사용(음성합성엔진을 이용한 오리지널 곡에 한함)에 대한
				저작권 허락이 포함되며,
				<br />'월간 한국 보카로P 신곡 소개(VO!CE CHART)' 영상의 제작 및 투고 이외에는 사용되지
				않음을 밝힙니다.
				<br /><br />(사용한 영상 및 음원 소스는 영상 투고 이후 폐기하는 것을 원칙으로 합니다)
			</h4>
			<br /><br />
			<h1 class="text-3xl text-base-content">신곡 수집 기준</h1>
			<br />
			<h4 class="text-base-content">
				1. VO!CE가 구독 중인 창작자의 노래를 포함하는 유튜브 영상
				<br /><br />2. 음성합성엔진을 이용한 오리지널 곡을 포함하는 유튜브 영상
				<br /><br />3. VO!CE가 구독 중인 채널에, 이전에 올린 오리지널 곡을 리메이크한 영상은
				포합되지 않습니다.
				<br /><br />4. 스트리밍 서비스(스포티파이, 유튜브 뮤직 등)에 발매된 곡이 있더라도, 유튜브에
				영상이 없다면 수집되지 않습니다.
				<br /><br />5. 오리지널 곡이 창작자 본인의 채널이 아닌 다른 채널에 올라갈 경우, 제가 인식할
				수 있는 범위에서 수집합니다. (따로 DM 주시면 확실하게 수집됩니다)
			</h4>
			<br /><br />
			<h4 class="text-base-content">
				아직 여러가지 미흡한 부분이 많이 있지만 부디 너그럽게 봐주시고,
				<br />문의사항이 있으시면 언제든지
				<a
					rel="noreferrer"
					href="https://twitter.com/rlarkspx"
					target="_blank"
					class="link link-hover"
				>
					<i class="fa-brands fa-twitter" /> 트위터 DM
				</a> 으로 말씀해주세요!
			</h4>
		</div>
	{/if}
	<div class="divider" />
	<!-- WARNING -->
	{#if show}
		<div
			class="grid card bg-error rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-3xl text-error-content">영상 시청시 주의사항</h1>
			<br /><br />
			<h4 class="text-xl text-error-content">
				<b>
					※ VO!CE의 모든 영상은 수익을 창출하지 않으며, 영상에 사용된 모든 영상과 음원은
					창작자분들께 사용 허락을 받았음을 밝힙니다.
					<br /><br />※ 몇몇 음원이 발매된 곡이 포함되어 있을 경우, 영상에 중간 광고가 포함될 수
					있습니다.
					<br />(광고로 인해 발생한 수익은 제가 아닌 창작자분들께 가는 것이니 참고하여 주세요!)
					<br /><br />※ 소개 영상의 곡 순서는 투고된 날짜 순이며, 곡의 인기와는 아무런 관계가
					없습니다.
					<br /><br />※ 개인이 채널을 운영하고 있기 때문에 투고되는 모든 신곡들을 파악하고, 직접
					영상 사용의 허락을 받기 어려운 환경에 있습니다.
					<br />따라서 창작분들의 자발적인 참여에 의존하고 있는 점 양해부탁드립니다.
					<br /><br />※ 본 영상은 모든 한국 보컬로이드 프로듀서분들의 노래를 포함하고 있지 않을 수
					있습니다.
					<br />자신이 알고 있는 곡들이 누락되어 있다면, 본 채널이 아니라 창작자분께서 참여하시도록
					말씀 부탁드립니다.
				</b>
			</h4>
			<br /><br />
		</div>
	{/if}
</section>

<style>
	section {
		padding: 8vh 0;
	}

	.card {
		width: 80vw;
		padding: 50px 40px;
		margin: 0 auto;
	}

	iframe {
		width: 95%;
		aspect-ratio: 16/9;
		border-radius: 15px;
		background-color: #999;
		margin-top: 2rem;
	}

	@media all and (min-width: 1024px) {
		iframe {
			width: 70%;
		}
	}
</style>
