<script lang="ts">
	// Skills configuration with custom SVG paths for Light Mode
</script>

<section class="skills-section">
	<div class="container skills-grid">
		<!-- Left Stack -->
		<div class="skills-stack stack-left">
			<!-- Skill 1: Fintech -->
			<div class="skill-pill glass-card">
				<span class="pill-dot"></span>
				<div class="glass-icon">
					<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
						<rect x="2" y="5" width="20" height="14" rx="2" ry="2" />
						<line x1="2" y1="10" x2="22" y2="10" />
					</svg>
				</div>
				<span class="pill-name text-sans">Fintech & Payments</span>
			</div>

			<!-- Skill 2: Telecom -->
			<div class="skill-pill glass-card">
				<span class="pill-dot"></span>
				<div class="glass-icon">
					<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
						<path d="M12 2a10 10 0 0 1 10 10" />
						<path d="M12 6a6 6 0 0 1 6 6" />
						<circle cx="12" cy="12" r="1" fill="currentColor" />
						<path d="M12 12v10" />
						<path d="m8 14 8 8" />
						<path d="m16 14-8 8" />
					</svg>
				</div>
				<span class="pill-name text-sans">Telecom Infrastructure</span>
			</div>

			<!-- Skill 3: Broadband -->
			<div class="skill-pill glass-card">
				<span class="pill-dot"></span>
				<div class="glass-icon">
					<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
						<path d="M5 12h14" />
						<path d="M12 5v14" />
						<circle cx="12" cy="5" r="3" fill="currentColor" fill-opacity="0.1" />
						<circle cx="5" cy="12" r="3" fill="currentColor" fill-opacity="0.1" />
						<circle cx="19" cy="12" r="3" fill="currentColor" fill-opacity="0.1" />
						<circle cx="12" cy="19" r="3" fill="currentColor" fill-opacity="0.1" />
					</svg>
				</div>
				<span class="pill-name text-sans">Broadband Systems</span>
			</div>
		</div>

		<!-- Central Statement -->
		<div class="skills-center">
			<span class="center-greeting text-serif italic">Hello!</span>
			<h3 class="center-thesis text-serif">
				focus is on blending <span class="italic text-accent font-light">clear strategy</span>, 
				digital infrastructure, and <span class="italic">digital accessibility</span> to 
				craft services that <span class="text-accent italic font-light">solve real problems</span> 
				across the African continent.
			</h3>
		</div>

		<!-- Right Stack -->
		<div class="skills-stack stack-right">
			<!-- Skill 4: Venture Building -->
			<div class="skill-pill glass-card">
				<span class="pill-dot"></span>
				<div class="glass-icon">
					<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
						<path d="M4.5 16.5c-1.5 1.5-2.5 3.5-2.5 5.5C4 22 6 21 7.5 19.5" />
						<path d="M12 12 4.5 19.5" />
						<path d="M9 15 15 9" />
						<path d="M12 4c.6-1 2.5-2 5.5-2s5 2.5 4 5.5-3 5-5.5 5.5-4-.6-4-4Z" fill="currentColor" fill-opacity="0.1" />
					</svg>
				</div>
				<span class="pill-name text-sans">Venture Building</span>
			</div>

			<!-- Skill 5: C-Suite -->
			<div class="skill-pill glass-card">
				<span class="pill-dot"></span>
				<div class="glass-icon">
					<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
						<path d="M6 3h12l4 6-10 12L2 9z" fill="currentColor" fill-opacity="0.1" />
						<path d="M11 3 8 9l4 12" />
						<path d="M13 3l3 6-4 12" />
					</svg>
				</div>
				<span class="pill-name text-sans">C-Suite Leadership</span>
			</div>

			<!-- Skill 6: Big Data -->
			<div class="skill-pill glass-card">
				<span class="pill-dot"></span>
				<div class="glass-icon">
					<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
						<ellipse cx="12" cy="5" rx="9" ry="3" fill="currentColor" fill-opacity="0.1" />
						<path d="M3 5v14c0 1.66 4 3 9 3s9-1.34 9-3V5" />
						<path d="M3 12c0 1.66 4 3 9 3s9-1.34 9-3" />
					</svg>
				</div>
				<span class="pill-name text-sans">Big Data Analytics</span>
			</div>
		</div>
	</div>
</section>

<style>
	.skills-section {
		padding-block: var(--spacing-lg);
		background: radial-gradient(circle at center, rgba(157, 255, 59, 0.08) 0%, transparent 60%);
		position: relative;
	}

	.skills-grid {
		display: grid;
		grid-template-columns: 1fr;
		gap: 3rem;
		align-items: center;
	}

	@media (min-width: 1024px) {
		.skills-grid {
			grid-template-columns: 1fr 2fr 1fr;
			gap: 2rem;
		}
	}

	/* Skills Stacks */
	.skills-stack {
		display: flex;
		flex-wrap: wrap;
		gap: 1.25rem;
		justify-content: center;
	}

	@media (min-width: 1024px) {
		.skills-stack {
			flex-direction: column;
		}
		.stack-left {
			align-items: flex-start;
		}
		.stack-right {
			align-items: flex-end;
		}
	}

	/* Skill Pill Styling */
	.skill-pill {
		display: inline-flex;
		align-items: center;
		gap: 0.75rem;
		padding: 0.5rem 1rem;
		border-radius: var(--border-radius-pill);
		background: #ffffff;
		border: 1px solid rgba(0, 0, 0, 0.04);
		box-shadow: 0 4px 15px rgba(0, 0, 0, 0.015);
		transition: var(--transition-medium);
		cursor: default;
		--pill-accent: var(--color-accent-dim); /* Unified cohesive branding */
	}

	.skill-pill:hover {
		transform: translateY(-3px) scale(1.03);
		box-shadow: 0 10px 25px rgba(157, 255, 59, 0.1);
		border-color: var(--pill-accent);
	}

	.pill-dot {
		width: 8px;
		height: 8px;
		border-radius: 50%;
		background-color: var(--pill-accent);
		box-shadow: 0 0 5px var(--pill-accent);
	}

	.pill-name {
		font-size: 0.85rem;
		font-weight: 700;
		color: var(--color-text-primary);
	}

	/* Central Thesis Statement */
	.skills-center {
		text-align: center;
		max-width: 700px;
		margin: 0 auto;
	}

	.center-greeting {
		font-size: clamp(1.8rem, 3vw, 2.5rem);
		color: var(--color-accent-dim);
		display: block;
		margin-bottom: 1.5rem;
		line-height: 1;
	}

	.center-thesis {
		font-size: clamp(1.8rem, 3.2vw, 3.2rem);
		font-weight: 300;
		line-height: 1.25;
		color: var(--color-text-primary);
		letter-spacing: -0.5px;
	}

	.italic {
		font-style: italic;
	}
	
	.font-light {
		font-weight: 300;
	}
</style>
