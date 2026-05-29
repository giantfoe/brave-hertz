<script lang="ts">
	import { onMount } from 'svelte';

	let visible = $state(false);

	onMount(() => {
		visible = true;
	});
</script>

<section class="hero" id="home" class:visible>
	<!-- Central Green Glowing Orb Behind Text & Portrait -->
	<div class="bg-glow-orb orb-hero"></div>

	<div class="container hero-container">
		<!-- 1. Headline Group (Centered in background) -->
		<div class="hero-headline-group">
			<h1 class="hero-title text-sans">Hi I'm David</h1>
			<h2 class="hero-subtitle text-serif">
				<span class="italic font-light">Tech</span> Founder
			</h2>
		</div>

		<!-- 2. Interactive Interactive Zone (Portrait & Floating Elements) -->
		<div class="hero-interactive-zone">
			<!-- Floating Left: Status Pill (Removed) -->
			<div class="hero-float-left">
			</div>

			<!-- Center: Overlapping Portrait -->
			<div class="hero-image-wrapper">
				<img 
					src="/david-headshot.png" 
					alt="David Kpakima Portrait" 
					class="hero-portrait"
					loading="eager"
				/>
			</div>

			<!-- Floating Right: Description Tagline -->
			<div class="hero-float-right">
				<p class="hero-tagline text-sans">
					passionate about building digital infrastructure and fintech networks that connect users with value.
				</p>
			</div>
		</div>

		<!-- 3. Bottom Row: Trusted Stack & CTA button -->
		<div class="hero-bottom-row">
			<!-- Bottom Left: Avatar Stack -->
			<div class="trust-container">
				<div class="avatar-stack">
					<div class="avatar av-1">
						<svg viewBox="0 0 32 32" fill="none" stroke="currentColor" stroke-width="2">
							<path d="M16 18a6 6 0 1 0 0-12 6 6 0 0 0 0 12ZM6 26a10 10 0 0 1 20 0" fill="currentColor" fill-opacity="0.1" />
						</svg>
					</div>
					<div class="avatar av-2">
						<svg viewBox="0 0 32 32" fill="none" stroke="currentColor" stroke-width="2">
							<path d="M16 18a6 6 0 1 0 0-12 6 6 0 0 0 0 12ZM6 26a10 10 0 0 1 20 0" fill="currentColor" fill-opacity="0.1" />
						</svg>
					</div>
					<div class="avatar av-3">
						<svg viewBox="0 0 32 32" fill="none" stroke="currentColor" stroke-width="2">
							<path d="M16 18a6 6 0 1 0 0-12 6 6 0 0 0 0 12ZM6 26a10 10 0 0 1 20 0" fill="currentColor" fill-opacity="0.1" />
						</svg>
					</div>
				</div>
				<p class="trust-text text-sans">
					Trusted by over <strong>1200+ partners</strong> across West African digital networks.
				</p>
			</div>

			<!-- Bottom Right: CTA Get in Touch Button -->
			<div class="cta-container">
				<a href="#contact" class="btn-primary hero-cta text-sans">
					<span>Get in Touch</span>
					<svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
						<line x1="7" y1="17" x2="17" y2="7"></line>
						<polyline points="7 7 17 7 17 17"></polyline>
					</svg>
				</a>
			</div>
		</div>
	</div>
</section>

<style>
	.hero {
		min-height: 100vh;
		display: flex;
		align-items: center;
		padding-top: 120px;
		padding-bottom: 2rem;
		position: relative;
		overflow: visible;
		background-color: var(--color-bg);
		opacity: 0;
		transform: translateY(10px);
		transition: opacity 1s cubic-bezier(0.16, 1, 0.3, 1), transform 1s cubic-bezier(0.16, 1, 0.3, 1);
		z-index: 15; /* Stack above the partner carousel to allow portrait overflow */
	}

	.hero.visible {
		opacity: 1;
		transform: translateY(0);
	}

	.orb-hero {
		top: 15%;
		left: 50%;
		transform: translateX(-50%);
		width: 60vw;
		height: 60vw;
		opacity: 0.9;
	}

	.hero-container {
		display: flex;
		flex-direction: column;
		position: relative;
		z-index: 10;
		width: 100%;
	}

	/* 1. Headline Group (Centered background text) */
	.hero-headline-group {
		text-align: center;
		margin-bottom: -4rem; /* pull interactive elements on top */
		position: relative;
		z-index: 1;
	}

	.hero-title {
		font-size: clamp(3.5rem, 9vw, 9.5rem);
		font-weight: 700;
		line-height: 0.9;
		letter-spacing: -3px;
		color: var(--color-text-primary);
	}

	.hero-subtitle {
		font-size: clamp(3.2rem, 8vw, 8.5rem);
		font-weight: 300;
		line-height: 0.9;
		letter-spacing: -2px;
		color: var(--color-text-primary);
		margin-top: 0.25rem;
	}

	.italic {
		font-style: italic;
	}

	.font-light {
		font-weight: 300;
	}

	/* 2. Interactive Zone (Portrait & Floaters) */
	.hero-interactive-zone {
		display: grid;
		grid-template-columns: 1fr;
		align-items: center;
		gap: 2rem;
		position: relative;
		z-index: 2;
	}

	@media (min-width: 1024px) {
		.hero-interactive-zone {
			grid-template-columns: 1fr auto 1fr;
			gap: 3rem;
		}
	}

	/* Center portrait card structure */
	.hero-image-wrapper {
		display: flex;
		justify-content: center;
		position: relative;
		width: 100%;
		max-width: 480px; /* Sized up on mobile */
		margin: -1rem auto -7rem; /* Lower top overlap, larger bottom overflow */
		z-index: 5;
	}

	@media (min-width: 1024px) {
		.hero-image-wrapper {
			max-width: 660px; /* Sized up on desktop */
			margin: -2.5rem auto -14rem; /* Lower top overlap, larger bottom overflow into next section */
		}
	}

	.hero-portrait {
		width: 100%;
		height: auto;
		display: block;
		object-fit: cover;
		mix-blend-mode: multiply; /* Blends portrait white background with the glowing neon gradient */
		transition: var(--transition-smooth);
	}

	/* Floating elements layout */
	.hero-float-left {
		display: flex;
		justify-content: center;
	}

	.hero-float-right {
		display: flex;
		justify-content: center;
		text-align: center;
	}

	@media (min-width: 1024px) {
		.hero-float-left {
			justify-content: flex-start;
			padding-top: 4rem;
		}

		.hero-float-right {
			justify-content: flex-end;
			text-align: left;
			padding-top: 4rem;
		}
	}

	/* Tagline */
	.hero-tagline {
		font-size: clamp(0.95rem, 1.2vw, 1.15rem);
		color: var(--color-text-secondary);
		line-height: 1.6;
		max-width: 320px;
	}

	/* 3. Bottom Row (Avatars & CTA) */
	.hero-bottom-row {
		display: flex;
		flex-direction: column;
		gap: 2rem;
		align-items: center;
		justify-content: space-between;
		margin-top: 3rem;
		border-top: 1px solid rgba(0, 0, 0, 0.05);
		padding-top: 2rem;
	}

	@media (min-width: 768px) {
		.hero-bottom-row {
			flex-direction: row;
		}
	}

	.trust-container {
		display: flex;
		align-items: center;
		gap: 1.25rem;
	}

	@media (max-width: 767px) {
		.trust-container {
			flex-direction: column;
			text-align: center;
		}
	}

	.avatar-stack {
		display: flex;
		align-items: center;
	}

	.avatar {
		width: 2.25rem;
		height: 2.25rem;
		border-radius: 50%;
		background: #f1f3f0;
		border: 2px solid var(--color-bg);
		display: flex;
		align-items: center;
		justify-content: center;
		color: var(--color-text-muted);
		overflow: hidden;
	}

	.avatar:not(:first-child) {
		margin-left: -0.75rem;
	}

	.trust-text {
		font-size: 0.85rem;
		color: var(--color-text-secondary);
		max-width: 300px;
		line-height: 1.4;
	}

	.cta-container {
		flex-shrink: 0;
	}
</style>
