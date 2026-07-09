<script lang="ts">
	import { page } from '$app/state';
	import Slide1 from '$lib/slides/Slide1.svelte';
	import Slide2 from '$lib/slides/Slide2.svelte';
	import Slide3 from '$lib/slides/Slide3.svelte';
	import Slide4 from '$lib/slides/Slide4.svelte';
	import Slide5 from '$lib/slides/Slide5.svelte';
	import Slide6 from '$lib/slides/Slide6.svelte';
	import Slide7 from '$lib/slides/Slide7.svelte';
	import Slide8 from '$lib/slides/Slide8.svelte';
	import Slide9 from '$lib/slides/Slide9.svelte';
	import Slide10 from '$lib/slides/Slide10.svelte';
	import Slide11 from '$lib/slides/Slide11.svelte';

	const slides = [
		Slide1,
		Slide2,
		Slide3,
		Slide4,
		Slide5,
		Slide6,
		Slide7,
		Slide8,
		Slide9,
		Slide10,
		Slide11
	];

	const idx = $derived(parseInt((page.params as { slide: string }).slide) - 1);
	const SlideComponent = $derived(slides[Math.max(0, Math.min(idx, slides.length - 1))]);
</script>

{#key (page.params as { slide: string }).slide}
	<SlideComponent />
{/key}
