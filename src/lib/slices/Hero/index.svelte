<script lang="ts">
	import type { Content } from '@prismicio/client';
	import { PrismicImage, PrismicLink, PrismicRichText } from '@prismicio/svelte';

	/** @type {import("@prismicio/client").Content.HeroSlice}*/

	export let slice: Content.HeroSlice;
</script>

<section data-slice-type={slice.slice_type} data-slice-variation={slice.variation}>
	<PrismicRichText field={slice.primary.heading}></PrismicRichText>
	<PrismicRichText field={slice.primary.paragraph}></PrismicRichText>
	<PrismicImage field={slice.primary.image} />
	<PrismicLink field={slice.primary.button_link}>{slice.primary.button_label}</PrismicLink>
</section>
