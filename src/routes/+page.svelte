<script>
	//reveal
	import { reveal } from 'svelte-reveal';
	import { copy } from 'svelte-copy';

	import { afterUpdate } from 'svelte';
	import { each, onMount } from 'svelte/internal';
	let show = false;
	afterUpdate(() => {
		show = true;
	});

	//store
	import { etcytkr, etcytjp } from './youtube';

	//toggle
	let toggleshow1 = false;
	let toggleshow2 = false;
	let toggleshow3 = false;

	//tab-active
	import { count } from './+page';
	onMount(() => {
		count.set(1);
	});
</script>

<svelte:head>
	<title>Byeol_Dasoni</title>
</svelte:head>

<section class="flex flex-col w-full">
	<!-- profile -->
	{#if show}
		<div
			class="grid card bg-primary-content rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 100,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<div class="flex items-center gap-10 flex-col xl:flex-row xl:items-start">
				<picture>
					<img src="/images/profile.png" alt="프로필 사진" class="profileImg" />
				</picture>
				<div class="text-center xl:text-left">
					<h1 class="text-3xl text-info-content">별다소니</h1>
					<h2 class="text-xl">서브컬쳐 작사가</h2>
					<ul class="flex flex-row gap-4 justify-center xl:justify-start">
						<li>
							<a href="mailto:rlarkspx@gmail.com" rel="noreferrer" target="_blank">
								<i class="fa-solid fa-envelope text-2xl" />
							</a>
						</li>
						<li>
							<a href="https://www.youtube.com/@BDSN_Official" rel="noreferrer" target="_blank">
								<i class="fa-brands fa-youtube text-2xl" />
							</a>
						</li>
						<li>
							<a href="https://byeol-dasoni.postype.com" rel="noreferrer" target="_blank">
								<i class="fa-solid fa-paragraph fa-flip-horizontal text-2xl" />
							</a>
						</li>
						<li>
							<button
								use:copy={`byeoldasoni`}
								on:svelte-copy={(event) => alert('Copied : ' + event.detail)}
								on:svelte-copy:error={(event) =>
									alert(`There was an error: ${event.detail.message}`)}
							>
								<i class="fa-brands fa-discord text-2xl" />
							</button>
						</li>
					</ul>
					<br />
					<p>
						<br />창작의 별을 탐구하는 작사가 입니다.
						<br /><a href="https://kre.pe/U1WP" rel="noreferrer" target="_blank">
							<b>작사 의뢰 및 문의는 크레페를 이용해 주세요!</b>
							<picture>
								<img src="/images/crepe.jpg" alt="프로필 사진" class="crepeImg" />
							</picture>
						</a>
						<br />
						<br />❄️'겨울이 있던 꽃' 팀장
						<br />✨'별의 바다에 가라앉고 있어' 팀장 (활동 종료)
					</p>
					<p>
						<br /> ▼ 외부 앨범 참여 목록 ▼<br />
						<br />💫Digital Singleㅣ"Starsign" 참여
						<br />🍀Digital Singleㅣ"괜찮아 괜찮아" 참여
						<br />📞Digital Singleㅣ"Phone Booth" 참여
						<br />🎉CDㅣ"Hello, space!-UNI 5th Anniversary Album-" 참여
						<br />🎉CD & Digitalㅣ"Re:Birth-SeeU 10th Anniversary Album-" 참여
						<br />🎺CDㅣ"첫 만남(初めての出会い)" 참여
					</p>
					<br />
					<!-- The button to open modal -->
					<label for="my-modal-4" class="modalbtn btn text-lg shadow-md bg-base-content text-white">
						의뢰 가격 및 주의사항
					</label>

					<!-- Put this part before </body> tag -->
					<input type="checkbox" id="my-modal-4" class="modal-toggle" />
					<label for="my-modal-4" class="modal cursor-pointer">
						<label class="modal-box relative" for="">
							<h3 class="text-2xl font-bold text-center">작사 의뢰시 주의사항</h3>
							<br />
							<p>
								1. 작사 의뢰할 때는 무엇보다도 예의를 지켜주세요. (저도 최대한 예의를 지키려
								노력하겠습니다)
							</p>
							<br />
							<p>
								2. 마감 기한을 말씀해주지 않으시면 기본적으로 '7일'입니다. (평균 작업 소요시간은
								1~3일 정도입니다)
							</p>
							<br />
							<p>
								3. 데모곡에 반드시 보컬 멜로디가 포함되어 있어야 합니다. (가사와 함께 작곡을
								해드리지 않습니다)
							</p>
							<br />
							<p>4. 언어는 한국어, 일본어 작사만 가능합니다.</p>
							<br />
							<p>
								5. 가사의 길이에 따른 할인은 없습니다. (가사의 길이와는 관계 없이 최선을 다해
								작사하고 있기 때문에 양해 부탁드립니다)
							</p>
							<br />
							<p>
								6. 가사의 컨펌 및 피드백은 기본적으로 '2회'까지이며, 자잘한 수정이 필요한 경우에는
								융통성 있게 해드릴 예정입니다.
							</p>
							<br />
							<p>
								7. 가사 작업이 시작된 이후에는 금액 환불이 불가능 합니다. 신중하게 의뢰해 주세요!
							</p>
							<br />
							<p>
								8. 의뢰 내용이 제가 추구하는 방향성과 다를 경우, 작사 의뢰를 거부할 수 있습니다.
							</p>
							<div class="divider" />
							<h3 class="text-lg font-bold">A 타입 : 비영리 사용</h3>
							<p class="py-4 indent-2">
								단순히 개인적인 곡을 제작하실 목적으로 가사를 사용하실 경우입니다. <b
									>가사를 이용하여 수익을 창출하지 않거나, 가사를 포함한 음원으로 얻는 수익이 미미한
									활동(유튜브 영상 업로드, 사운드 클라우드 업로드 등)</b
								>이 이에 해당됩니다.
							</p>
							<h3 class="text-md font-bold">가격 : 30,000원~100,000원 (자유 후원)</h3>
							<div class="divider" />
							<h3 class="text-lg font-bold">B 타입 : 음원 발매용</h3>
							<p class="py-4 indent-2">
								<b
									>가사를 포함한 음원을 음반 및 스트리밍 서비스에 등록하거나 기타 영리적인
									활동(미디어 콘텐츠 OST, 개인 방송용 음원 등)을 하는 경우입니다.</b
								> 이 경우에는 가사에 대한 모든 저작권 및 사용권이 작사가에게 있으며, 그에 따른 저작권료를
								요구할 수 있습니다.
							</p>
							<h3 class="text-md font-bold">가격 : 200,000원</h3>
							<div class="divider" />
							<h3 class="text-lg font-bold">C 타입 : 기업/단체의 영리적 이용</h3>
							<p class="py-4 indent-2">
								<b>기업 및 단체의 영리적 활동의 목적으로 가사를 사용할 경우입니다.</b> 가사의 사용권(라이센스)을
								양도하며, 별도의 저작권료를 요구하지 않습니다. (단, 저작 인격권을 침해할 경우에는 가사의
								사용을 제한할 수 있습니다)
							</p>
							<h3 class="text-md font-bold">가격 : 700,000원</h3>
						</label>
					</label>
				</div>
			</div>
		</div>
	{/if}
	<div class="divider" />
	<!-- 신곡 -->
	{#if show}
		<div
			class="grid card bg-neutral-content rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-3xl text-info-content uppercase">❗NEW❗</h1>
			<br />
			<iframe
				src="https://www.youtube.com/embed/Ir09TxDDOzI?si=_ihKY2z2BHIhRamk"
				title="YouTube video player"
				frameborder="0"
				allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
				allowfullscreen
				use:reveal={{ transition: 'fly' }}
			/>
		</div>
	{/if}
	<div class="divider" />
	<!-- awords -->
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
			<h1 class="text-2xl text-info-content">수상경력</h1>
			<br />
			<h2 class="text-xl">새로운 경기도 노래 공정한 공모전<br />🏆작사부문 대상🏆</h2>
			<br />
			<input type="checkbox" class="toggle toggle-neutral" bind:checked={toggleshow1} />
			{#if toggleshow1}
				<iframe
					src="https://www.youtube.com/embed/eGmztNGkBOo"
					title="YouTube video player"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
					use:reveal={{ transition: 'fly' }}
				/>
				<iframe
					src="https://www.youtube.com/embed/PvuZNBbuN4g"
					title="YouTube video player"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
					use:reveal={{ transition: 'fly' }}
				/>
				<iframe
					src="https://www.youtube.com/embed/uEdxNzsdwZE"
					title="YouTube video player"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
					use:reveal={{ transition: 'fly' }}
				/>
			{/if}
		</div>
	{/if}
	<div class="divider" />
	<!-- 기타 작업물 한국어 -->
	{#if show}
		<div
			class="grid card bg-warning rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-2xl text-info-content">한국어 작사 작업물<br /><small>(최신순)</small></h1>
			<br />
			<input type="checkbox" class="toggle toggle-neutral" bind:checked={toggleshow2} />
			<br />
			{#if toggleshow2}
				{#each etcytkr as yt}
					<!-- content here -->
					<iframe
						src="https://www.youtube.com/embed/{yt.src}"
						title="YouTube video player"
						frameborder="0"
						allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
						allowfullscreen
						use:reveal={{ transition: 'fly' }}
					/>
					<br />
					<h2>〈 {yt.name} 〉</h2>
				{/each}
			{/if}
		</div>
	{/if}
	<div class="divider" />
	<!-- 기타 작업물 일본어 -->
	{#if show}
		<div
			class="grid card bg-warning rounded-box place-items-center shadow-2xl"
			use:reveal={{
				threshold: 0.0,
				delay: 300,
				duration: 500,
				transition: 'blur',
				blur: 20,
				opacity: 0.5
			}}
		>
			<h1 class="text-2xl text-info-content">일본어 작사 작업물<br /><small>(최신순)</small></h1>
			<br />
			<input type="checkbox" class="toggle toggle-neutral" bind:checked={toggleshow3} />
			<br />
			{#if toggleshow3}
				{#each etcytjp as yt}
					<!-- content here -->
					<iframe
						src="https://www.youtube.com/embed/{yt.src}"
						title="YouTube video player"
						frameborder="0"
						allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
						allowfullscreen
						use:reveal={{ transition: 'fly' }}
					/>
					<br />
					<h2>〈 {yt.name} 〉</h2>
				{/each}
			{/if}
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

	.profileImg {
		width: 180px;
		border-radius: 15%;
	}

	.crepeImg {
		display: inline;
		width: 25px;
		border-radius: 15%;
	}

	iframe {
		width: 95%;
		aspect-ratio: 16/9;
		border-radius: 15px;
		background-color: #999;
		margin-top: 2rem;
	}

	.modalbtn {
		font-family: var(--cfont);
		font-weight: bolder;
	}

	@media all and (min-width: 1024px) {
		iframe {
			width: 70%;
		}
	}
</style>
