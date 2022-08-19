<script lang="ts">
	import { flip } from 'svelte/animate';
	//APIs
	export let images: any; //input obj

	export let containerWidth = '80vw'; //container size
	export let imageWidth = '60vw'; //img size
	export let imageGap = '15vw'; //img size

	export let titleColor = '#fafaf9'; //img-title color
	export let titleSize = '2vh'; //img-title color

	export let btnShown = ''; //button display
	export let btnColor = '#666'; //controll button color
	export let btnSize = '2em'; //controll button size

	export let speed = 500; //duraition

	//controll button
	const rotateLeft = () => {
		const transitioningImage = images[images.length - 1];
		let tr = document.getElementById(transitioningImage.name) as HTMLDivElement;
		tr.style.opacity = '0';
		images = [images[images.length - 1], ...images.slice(0, images.length - 1)];
		setTimeout(() => {
			tr.style.opacity = '1';
		}, speed);
	};

	const rotateRight = () => {
		const transitioningImage = images[0];
		let tr = document.getElementById(transitioningImage.name) as HTMLDivElement;
		images = [...images.slice(1, images.length), images[0]];
		setTimeout(() => {
			tr.style.opacity = '1';
		}, speed);
	};
</script>

<!-- container box -->
<div id="carousel-container" style={`width: ${containerWidth};`}>
	<!-- flex box -->
	<ul id="carousel-images" style={`gap: ${imageGap}`}>
		{#each images as image (image)}
			<!-- flex items -->
			<li id={image.name} animate:flip={{ duration: speed }}>
				<iframe
					src="https://www.youtube.com/embed/{image.src}"
					title={image.name}
					frameborder="0"
					allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
					allowfullscreen
					style={`width: ${imageWidth};`}
				/>
				<h2
					class="img-title"
					style={`color: ${titleColor}; font-size: ${titleSize}; text-align: center; margin-top: 1.5em;`}
				>
					{image.name}
				</h2>
			</li>
		{/each}
	</ul>

	<!-- controll button -->
	<button
		class="left"
		style={`color: ${btnColor}; font-size: ${btnSize}; display: ${btnShown}`}
		on:click={rotateLeft}
	>
		<i class="fa-solid fa-chevron-left" style={`display: ${btnShown}`} /></button
	>

	<button
		class="right"
		style={`color: ${btnColor}; font-size: ${btnSize}; display: ${btnShown}`}
		on:click={rotateRight}
	>
		<i class="fa-solid fa-chevron-right" style={`display: ${btnShown}`} /></button
	>
</div>

<style>
	#carousel-container {
		margin: 0 auto;
		position: relative;
		overflow-x: hidden;
	}

	button {
		position: absolute;
		top: 50%;
		transform: translateY(-50%);
		z-index: 100;
	}

	.left {
		left: 2%;
	}

	.right {
		right: 2%;
	}

	button:hover {
		transition: all 0.3s ease;
		color: rgb(208, 38, 38);
	}

	#carousel-images {
		display: flex;
		justify-content: center;
		flex-wrap: nowrap;
	}
</style>
