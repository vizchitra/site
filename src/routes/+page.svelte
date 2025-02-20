<script lang="ts">
	import BannerPolygon from '$lib/components/BannerPolygon.svelte';
	import PolygonDivider from '$lib/components/PolygonDivider.svelte';
	import VizchitraLogo from '$lib/assets/images/viz-logo-animate.svg?raw';
	import { formatSlantedText } from '$lib/utils/utils.js';
	import CallToAction from '$lib/components/CallToAction.svelte';
	import VizChitraLogoType from '$lib/components/VizChitraLogoType.svelte';
	import Button from '$lib/components/Button.svelte';
	import TeamSection from '$lib/components/TeamSection/TeamSection.svelte';

	export let data;
</script>

<svelte:head>
	<!-- <title>Home</title>
	<meta name="description" content="Svelte demo app" />
	<meta
		name="viewport"
		content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"
	/> -->
	<link
		rel="preload"
		href="/fonts/Cairo-Variable-Latin.woff2"
		as="font"
		type="font/woff2"
		crossorigin
	/>
	<link
		rel="preload"
		href="/fonts/IBMPlexSans-Regular-Latin1.woff2"
		as="font"
		type="font/woff2"
		crossorigin
	/>
</svelte:head>

<div class="banner-container full-bleed relative h-[100svh]">
	<BannerPolygon />
	<div
		class="logo-container pointer-events-none absolute top-1/3 left-1/2 mb-2 flex -translate-x-1/2 -translate-y-1/3 flex-col items-center rounded-md bg-white px-2 pt-2 pb-4 shadow-lg md:max-w-none md:flex-row md:gap-0 md:px-8"
	>
		<div class="logo">
			{@html VizchitraLogo}
		</div>

		<h3
			class="tagline -mt-8 max-w-[20ch] border-black text-center uppercase md:mt-0 md:border-l-2 md:pl-5 md:text-left"
		>
			{#each formatSlantedText('A SPACE TO CONNECT AND CREATE WITH DATA') as letter}
				<span
					class="slanted-text text-[18px] md:text-[20px]"
					style="--letter-slant: {letter.slant}"
				>
					{letter.letter}
				</span>
			{/each}
		</h3>
	</div>
</div>

<CallToAction />

<div class="mt-20 flex flex-col items-center gap-10">
	<div class="content-container flex flex-col gap-2">
		<h1>
			<VizChitraLogoType></VizChitraLogoType>
		</h1>

		<p class="content-text mb-4 max-w-[55ch]">
			Data visualization practitioners in India have been spread across different communities. As
			the first of its kind <span class="font-semibold">
				data visualization community, VizChitra
			</span> is putting together a conference to bring these people together.
		</p>

		<p class="mx-auto mt-2 mb-6">
			{#each formatSlantedText('A SPACE TO CONNECT AND CREATE WITH DATA') as letter}
				<span class="slanted-text text-[18px] md:text-[24px]" style="--letter-slant: {letter.slant}">
					{letter.letter}
				</span>
			{/each}
		</p>

		<div class="pillars">
			<p class="content-text mb-1 max-w-[55ch]">
				Our goal is to build a community of diverse, interdisciplinary individuals working across
				the visualization spectrum, and facilitate learning and connections between people from
				different industries and disciplines who share a common interest in the power of data and
				storytelling.
			</p>
		</div>

		<PolygonDivider></PolygonDivider>
	</div>

	<div class="content-container flex flex-col gap-2">
		<h2 class="content-heading !text-[2rem]">OUR MISSION</h2>

		<p class="content-text mb-4 max-w-[55ch]">
			To foster a vibrant <span class="font-semibold">community of data storytellers in India</span
			>, bridging technical analysis and design expertise to shape perspectives and drive change
		</p>

		<p class="mx-auto mb-6 text-center">
			{#each formatSlantedText('AN INDIAN DATA VISUALIZATION COMMUNITY') as letter}
				<span
					class="slanted-text text-[18px] md:text-[24px]"
					style="--letter-slant: {letter.slant}"
				>
					{letter.letter}
				</span>
			{/each}
		</p>

		<div class="pillars">
			<p class="content-text mb-1 max-w-[55ch]">
				The VizChitra community plans to drive this using these three main pillars of work:
			</p>
			<ol class="mt-4 space-y-6">
				<li>
					<h3 class="content-heading">1. Consider and Curate:</h3>
					<p class="content-text">
						Build a rhythm of curated events to spread the practice of data visualization
					</p>
				</li>
				<li>
					<h3 class="content-heading">2. Cultivate and Care:</h3>
					<p class="content-text">
						Nurture a fertile space for learning and sharing of data visualization skills
					</p>
				</li>

				<li>
					<h3 class="content-heading">3. Create and Collaborate:</h3>
					<p class="content-text">
						Express and co-create to push the boundaries of data visualization
					</p>
				</li>
			</ol>
		</div>

		<PolygonDivider></PolygonDivider>

		<h2 class="font-display text-left !text-[2rem] font-bold">MEET THE TEAM</h2>
	</div>
	<div>
		<TeamSection></TeamSection>
	</div>

	<div>
		<PolygonDivider></PolygonDivider>
		<h2 class="content-heading mt-5 !text-[2rem]">VIZCHITRA 2025</h2>

		<p class="content-text mb-6 max-w-[55ch]">
			One day of talks and dialogues and one day of workshops
		</p>

		<div class="content-notice mb-10 grid grid-cols-1 gap-6 md:grid-cols-2 md:gap-8">
			<div class="space-y-2">
				<h3 class="content-heading text-primary">CONFERENCE DAY</h3>
				<div class="space-y-1">
					<p class="content-text font-semibold">27th June, 2025</p>
					<p class="text-[20px]">Bangalore International Center</p>
				</div>
			</div>

			<div class="space-y-2">
				<h3 class="content-heading text-primary">WORKSHOP DAY</h3>
				<div class="space-y-1">
					<p class="content-text font-semibold">28th June, 2025</p>
					<p class="text-[20px]">Across Bangalore</p>
				</div>
			</div>
		</div>
		<Button
			class_name="w-full"
			variant="primary"
			href="https://hasgeek.com/VizChitra/2025/"
			external>Add us to your calendar!</Button
		>

		<PolygonDivider></PolygonDivider>
	</div>
</div>

<style>
	.banner-container {
		width: 100vw;
		position: relative;
	}

	.banner-container::before,
	.banner-container::after {
		content: '';
		position: absolute;
		left: 0;
		right: 0;
		height: 25vh;
		pointer-events: none;
		z-index: 1;
	}

	@media (min-width: 768px) {
		.banner-container::before,
		.banner-container::after {
			height: 40vh;
		}
	}

	.banner-container::before {
		top: 0;
		background: linear-gradient(
			to bottom,
			rgb(255 255 255) 0%,
			rgba(255, 255, 255, 0.8) 5%,
			transparent 100%
		);
	}

	.banner-container::after {
		bottom: 0;
		background: linear-gradient(
			to top,
			rgb(255 255 255) 0%,
			rgba(255, 255, 255, 0.8) 5%,
			transparent 100%
		);
	}
</style>
