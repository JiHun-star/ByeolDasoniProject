<script lang="ts">
	import Carousel from '../components/carousel.svelte';
	import { binkan, yeoreum, byeoljari, dongyang } from '$lib/youtube';
</script>

<svelte:head>
	<title>합작 기획</title>
</svelte:head>

<Carousel images={byeoljari} />

<style>
	@media screen and (min-width: 320px) {
	}

	@media screen and (min-width: 768px) {
	}

	@media screen and (min-width: 1024px) {
	}
</style>
