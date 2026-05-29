<script lang="ts">
	import Header from '$lib/components/Header.svelte';
	import Hero from '$lib/components/Hero.svelte';
	import PartnerCarousel from '$lib/components/PartnerCarousel.svelte';
	import Ventures from '$lib/components/Ventures.svelte';
	import Skills from '$lib/components/Skills.svelte';
	import Timeline from '$lib/components/Timeline.svelte';
	import NewsTransparency from '$lib/components/NewsTransparency.svelte';
	import About from '$lib/components/About.svelte';
	import ContactForm from '$lib/components/ContactForm.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
	<title>David Kpakima | Tech Founder & Digital Infrastructure Leader</title>
</svelte:head>

<Header />

<main>
	<Hero />
	<PartnerCarousel />
	<Ventures />
	<Skills />
	<Timeline />
	<NewsTransparency />
	<About />
	<ContactForm />
</main>

<Footer />

