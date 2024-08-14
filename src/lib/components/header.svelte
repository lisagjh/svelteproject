<script>
	import Logo from '$lib/components/logo.svelte';
	import ButtonLink from '$lib/components/buttonLink.svelte';
	import { PrismicLink } from '@prismicio/svelte';

	/** @type {import("@prismicio/client").Content.SettingsDocument}*/
	export let settings;
</script>

<header>
	<nav
		class="flex flex-row items-center justify-between gap-6 px-5 py-3 md:flex-row"
		aria-label="Main"
	>
		<a href="/">
			<Logo />
			<span class="sr-only">{settings.data.site_title} homepage</span>
		</a>

		<ul class="flex gap-6">
			{#each settings.data.navigation as item (item.label)}
				{#if item.cta_button}
					<li>
						<ButtonLink field={item.link}>
							{item.label}</ButtonLink
						>
					</li>
				{:else}
					<li>
						<PrismicLink field={item.link} class="inline-flex min-h-11 items-center">
							{item.label}
						</PrismicLink>
					</li>
				{/if}
			{/each}
		</ul>
	</nav>
</header>
