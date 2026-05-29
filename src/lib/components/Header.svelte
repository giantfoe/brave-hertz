<script lang="ts">
	import { onMount } from 'svelte';

	let isMenuOpen = $state(false);
	let isScrolled = $state(false);

	function toggleMenu() {
		isMenuOpen = !isMenuOpen;
		if (isMenuOpen) {
			document.body.style.overflow = 'hidden';
		} else {
			document.body.style.overflow = '';
		}
	}

	function closeMenu() {
		isMenuOpen = false;
		document.body.style.overflow = '';
	}

	onMount(() => {
		const handleScroll = () => {
			isScrolled = window.scrollY > 20;
		};
		window.addEventListener('scroll', handleScroll);
		return () => {
			window.removeEventListener('scroll', handleScroll);
		};
	});
</script>

<header class="header" class:scrolled={isScrolled}>
	<div class="header-container">
		<!-- Brand Logo -->
		<a href="/" class="logo text-serif italic" onclick={closeMenu}>
			David Kpakima
		</a>

		<!-- Middle Award Badge -->
		<div class="badge-award">
			<!-- Left Laurel Wreath Branch -->
			<svg class="laurel-branch laurel-left" viewBox="0 0 32 64" fill="currentColor">
				<!-- Curve branch line -->
				<path d="M28 58C18 52 10 40 10 26C10 15 17 6 28 2" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
				<!-- Left leaves pointing upwards -->
				<path d="M 26 52 C 21 51, 19 46, 21 43 C 25 41, 27 44, 28 48 Z" />
				<path d="M 20 44 C 15 42, 13 37, 15 34 C 19 32, 21 35, 22 39 Z" />
				<path d="M 15 35 C 10 32, 8 27, 10 24 C 14 22, 16 25, 17 29 Z" />
				<path d="M 12 25 C 8 21, 7 15, 10 13 C 13 12, 15 15, 15 19 Z" />
				<path d="M 14 15 C 11 10, 11 4, 14 3 C 17 3, 18 7, 17 11 Z" />
				<path d="M 20 7 C 18 2, 20 0, 23 0 C 25 1, 25 5, 23 7 Z" />
			</svg>

			<!-- Center Content: Crown, Text, Divider -->
			<div class="award-center">
				<!-- Tiny gold Crown -->
				<svg class="award-crown" viewBox="0 0 24 24" fill="currentColor">
					<path d="M2 19h20v2H2z M21 7l-3.5 4.5L12 5 6.5 11.5 3 7v10h18V7z"/>
				</svg>
				
				<div class="award-text-group">
					<span class="award-title text-sans">Digital Infrastructure</span>
					<span class="award-subtitle text-serif">Leader</span>
					<!-- Mini Divider Line with Diamond -->
					<div class="award-divider">
						<span class="divider-line"></span>
						<span class="divider-diamond"></span>
						<span class="divider-line"></span>
					</div>
					<span class="award-year text-sans">2026</span>
				</div>
			</div>

			<!-- Right Laurel Wreath Branch -->
			<svg class="laurel-branch laurel-right" viewBox="0 0 32 64" fill="currentColor">
				<!-- Curve branch line -->
				<path d="M4 58C14 52 22 40 22 26C22 15 15 6 4 2" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
				<!-- Right leaves pointing upwards -->
				<path d="M 6 52 C 11 51, 13 46, 11 43 C 7 41, 5 44, 4 48 Z" />
				<path d="M 12 44 C 17 42, 19 37, 17 34 C 13 32, 11 35, 10 39 Z" />
				<path d="M 17 35 C 22 32, 24 27, 22 24 C 18 22, 16 25, 15 29 Z" />
				<path d="M 20 25 C 24 21, 25 15, 22 13 C 19 12, 17 15, 17 19 Z" />
				<path d="M 18 15 C 21 10, 21 4, 18 3 C 15 3, 14 7, 15 11 Z" />
				<path d="M 12 7 C 14 2, 12 0, 9 0 C 7 1, 7 5, 9 7 Z" />
			</svg>
		</div>

		<!-- Hamburger Menu Button -->
		<button 
			class="menu-toggle" 
			class:open={isMenuOpen} 
			aria-label="Toggle Navigation Menu" 
			aria-expanded={isMenuOpen}
			onclick={toggleMenu}
		>
			<span class="line line-1"></span>
			<span class="line line-2"></span>
			<span class="line line-3"></span>
		</button>
	</div>
</header>

<!-- Slide-Out Glassmorphic Menu -->
<nav class="navigation-overlay" class:open={isMenuOpen}>
	<div class="nav-links">
		<a href="#home" class="nav-link" onclick={closeMenu}>
			<span class="nav-num">01</span> <span class="nav-text text-serif">Home</span>
		</a>
		<a href="#about" class="nav-link" onclick={closeMenu}>
			<span class="nav-num">02</span> <span class="nav-text text-serif">Biography</span>
		</a>
		<a href="#ventures" class="nav-link" onclick={closeMenu}>
			<span class="nav-num">03</span> <span class="nav-text text-serif">Ventures</span>
		</a>
		<a href="#timeline" class="nav-link" onclick={closeMenu}>
			<span class="nav-num">04</span> <span class="nav-text text-serif">Timeline</span>
		</a>
		<a href="#news" class="nav-link" onclick={closeMenu}>
			<span class="nav-num">05</span> <span class="nav-text text-serif">News & Transparency</span>
		</a>
		<a href="#contact" class="nav-link" onclick={closeMenu}>
			<span class="nav-num">06</span> <span class="nav-text text-serif">Contact & Speaking</span>
		</a>
	</div>
</nav>

<style>
	.header {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		z-index: 1000;
		padding-block: 1.5rem;
		transition: var(--transition-medium);
	}

	.header.scrolled {
		padding-block: 1rem;
		background: rgba(255, 255, 255, 0.85);
		backdrop-filter: blur(12px);
		border-bottom: 1px solid rgba(157, 255, 59, 0.2);
		box-shadow: 0 4px 20px rgba(0, 0, 0, 0.02);
	}

	.header-container {
		max-width: var(--max-width);
		margin: 0 auto;
		padding-inline: var(--spacing-md);
		display: flex;
		justify-content: space-between;
		align-items: center;
		position: relative; /* Anchor absolute children like the award badge */
	}

	.logo {
		font-size: clamp(1.2rem, 2vw, 1.8rem);
		font-weight: 500;
		color: var(--color-text-primary);
		letter-spacing: -0.5px;
		z-index: 1010;
		transition: var(--transition-quick);
	}

	.logo:hover {
		color: var(--color-accent-dim);
	}

	/* Gold Award Badge styles */
	.badge-award {
		display: flex;
		align-items: center;
		gap: 0.65rem;
		background: linear-gradient(135deg, rgba(15, 19, 11, 0.96) 0%, rgba(26, 32, 20, 0.96) 100%);
		border: 1.5px solid rgba(223, 177, 91, 0.35);
		padding: 0.5rem 1.25rem;
		border-radius: 12px; /* High-end metal plaque look */
		box-shadow: 0 10px 30px rgba(0, 0, 0, 0.12), 0 0 15px rgba(223, 177, 91, 0.05);
		backdrop-filter: blur(12px);
		-webkit-backdrop-filter: blur(12px);
		z-index: 1010;
		transition: var(--transition-smooth);
		color: #DFB15B; /* Warm gold */
		position: absolute; /* Viewport centering */
		left: 50%;
		transform: translateX(-50%);
		overflow: hidden;
	}

	@media (max-width: 768px) {
		.badge-award {
			display: none; /* Hide on mobile/tablet to save header space */
		}
	}

	.badge-award::after {
		content: '';
		position: absolute;
		top: -50%;
		left: -60%;
		width: 30%;
		height: 200%;
		background: linear-gradient(
			to right,
			rgba(255, 255, 255, 0) 0%,
			rgba(255, 255, 255, 0.5) 50%,
			rgba(255, 255, 255, 0) 100%
		);
		transform: rotate(30deg);
		transition: all 0.8s cubic-bezier(0.16, 1, 0.3, 1);
		pointer-events: none;
		opacity: 0;
	}

	.badge-award:hover {
		border-color: #DFB15B;
		transform: translateX(-50%) translateY(-2px) scale(1.02); /* Maintain absolute centering on hover */
		box-shadow: 0 15px 35px rgba(223, 177, 91, 0.22);
	}

	.badge-award:hover::after {
		left: 140%;
		opacity: 1;
	}

	.laurel-branch {
		width: 1.5rem;
		height: 3rem;
		flex-shrink: 0;
		color: #DFB15B;
		transition: var(--transition-medium);
	}

	.badge-award:hover .laurel-left {
		transform: rotate(-5deg) translateX(-2px);
	}

	.badge-award:hover .laurel-right {
		transform: rotate(5deg) translateX(2px);
	}

	.award-center {
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
		gap: 0.1rem;
	}

	.award-crown {
		width: 1.15rem;
		height: 1.15rem;
		color: #DFB15B;
		margin-bottom: 0.05rem;
		transition: var(--transition-medium);
	}

	.badge-award:hover .award-crown {
		transform: translateY(-2px) scale(1.15);
		filter: drop-shadow(0 0 5px rgba(223, 177, 91, 0.6));
	}

	.award-text-group {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.award-title {
		font-size: 0.58rem;
		font-weight: 700;
		text-transform: uppercase;
		letter-spacing: 1px;
		color: rgba(255, 255, 255, 0.95);
		line-height: 1.2;
	}

	.award-subtitle {
		font-size: 0.72rem;
		font-weight: 400;
		font-style: italic;
		color: #DFB15B;
		letter-spacing: 0.5px;
		line-height: 1.1;
	}

	.award-divider {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 0.25rem;
		width: 100%;
		margin-block: 0.15rem;
	}

	.divider-line {
		width: 15px;
		height: 1px;
		background: rgba(223, 177, 91, 0.35);
	}

	.divider-diamond {
		width: 3px;
		height: 3px;
		background: #DFB15B;
		transform: rotate(45deg);
	}

	.award-year {
		font-size: 0.55rem;
		font-weight: 800;
		letter-spacing: 1.5px;
		color: rgba(255, 255, 255, 0.7);
	}

	/* Hamburger Button */
	.menu-toggle {
		background: rgba(0, 0, 0, 0.02);
		border: 1px solid rgba(0, 0, 0, 0.06);
		width: 3.5rem;
		height: 3.5rem;
		border-radius: 50%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		gap: 5px;
		cursor: pointer;
		z-index: 1010;
		transition: var(--transition-medium);
	}

	.menu-toggle:hover {
		background: rgba(157, 255, 59, 0.1);
		border-color: var(--color-accent-dim);
		transform: scale(1.05);
	}

	.line {
		width: 1.25rem;
		height: 2px;
		background: var(--color-text-primary);
		border-radius: 1px;
		transition: var(--transition-medium);
		transform-origin: center;
	}

	.menu-toggle.open .line-1 {
		transform: translateY(7px) rotate(45deg);
		background: var(--color-text-primary);
	}

	.menu-toggle.open .line-2 {
		opacity: 0;
	}

	.menu-toggle.open .line-3 {
		transform: translateY(-7px) rotate(-45deg);
		background: var(--color-text-primary);
	}

	/* Sliding navigation panel */
	.navigation-overlay {
		position: fixed;
		top: 0;
		right: 0;
		width: 100%;
		height: 100vh;
		background: rgba(255, 255, 255, 0.98);
		backdrop-filter: blur(20px);
		-webkit-backdrop-filter: blur(20px);
		z-index: 999;
		display: flex;
		align-items: center;
		justify-content: center;
		transform: translateX(100%);
		transition: transform 0.6s cubic-bezier(0.16, 1, 0.3, 1);
		border-left: 1px solid rgba(0, 0, 0, 0.05);
	}

	@media (min-width: 768px) {
		.navigation-overlay {
			width: 450px;
		}
	}

	.navigation-overlay.open {
		transform: translateX(0);
	}

	.nav-links {
		display: flex;
		flex-direction: column;
		gap: 2rem;
		padding: 2rem;
		width: 100%;
		max-width: 320px;
	}

	.nav-link {
		display: flex;
		align-items: center;
		gap: 1.5rem;
		color: var(--color-text-secondary);
		transition: var(--transition-medium);
		position: relative;
	}

	.nav-num {
		font-size: 0.85rem;
		font-family: var(--font-sans);
		font-weight: 700;
		color: var(--color-accent-dim);
	}

	.nav-text {
		font-size: clamp(1.8rem, 3vw, 2.4rem);
		font-weight: 400;
		color: var(--color-text-primary);
		transition: var(--transition-medium);
	}

	.nav-link:hover .nav-text {
		color: var(--color-accent-dim);
		transform: translateX(10px);
	}
</style>
