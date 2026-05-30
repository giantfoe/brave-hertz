<script lang="ts">
	// Personal stats for Light Mode
	const details = [
		{ label: 'Role / Title', value: 'Founder & Executive Director' },
		{ label: 'Education', value: 'BSc Business Administration (University of Sierra Leone)' },
		{ label: 'Experience', value: '15+ Years in Telecom & Fintech' },
		{ label: 'Location', value: 'Freetown, Sierra Leone' }
	];
</script>

<section class="about-section" id="about">
	<div class="container about-grid">
		<!-- Left: Stylized tilted grayscaled image -->
		<div class="about-image-col">
			<div class="image-tilt-frame">
				<img 
					src="/david-headshot.png" 
					alt="David Kpakima Portrait" 
					class="about-img"
					loading="lazy"
				/>
			</div>
		</div>

		<!-- Right: Biography, Stats Table and Socials -->
		<div class="about-content-col">
			<span class="section-tag text-serif italic">/ Biography</span>
			<h2 class="about-title text-sans">
				Pushing <span class="text-serif italic font-light">Boundaries</span> since 2010
			</h2>

			<div class="about-bio text-sans">
				<p>
					David Tamba Abdulai Kpakima is a prominent Sierra Leonean technology entrepreneur, digital infrastructure leader, and fintech builder. Drawing on early corporate banking and telecom marketing roles, he has co-founded and steered multiple companies that form the backbone of Sierra Leone's digital economy.
				</p>
				<p>
					As a passionate big data advocate and liberal innovator, David is dedicated to constructing disruptive fintech solutions and broadband speedways that empower local businesses, drive jobs, and expand broadband accessibility across West Africa.
				</p>
			</div>

			<!-- Details Table -->
			<div class="details-table text-sans">
				{#each details as detail}
					<div class="details-row">
						<span class="detail-label text-muted">{detail.label}</span>
						<span class="detail-value">{detail.value}</span>
					</div>
				{/each}
			</div>

			<!-- Social Links -->
			<div class="social-links-row">
				<a href="https://linkedin.com" target="_blank" rel="noopener noreferrer" class="social-link" aria-label="LinkedIn Profile">
					<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
						<path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path>
						<rect x="2" y="9" width="4" height="12"></rect>
						<circle cx="4" cy="4" r="2"></circle>
					</svg>
				</a>
				<a href="https://x.com/DKpakima" target="_blank" rel="noopener noreferrer" class="social-link" aria-label="Twitter X Profile">
					<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
						<path d="M22 4s-.7 2.1-2 3.4c1.6 10-9.4 17.3-18 11.6 2.2.1 4.4-.6 6-2C3 15.5.5 9.6 3 5c2.2 2.6 5.6 4.1 9 4-.9-4.2 4-6.6 7-3.8 1.1 0 3-1.2 3-1.2z"></path>
					</svg>
				</a>
				<a href="https://github.com" target="_blank" rel="noopener noreferrer" class="social-link" aria-label="Github Profile">
					<svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
						<path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path>
					</svg>
				</a>
			</div>
		</div>
	</div>
</section>

<style>
	.about-section {
		border-top: 1px solid rgba(0, 0, 0, 0.05);
		background-color: var(--color-bg);
		position: relative;
	}

	.about-grid {
		display: grid;
		grid-template-columns: 1fr;
		gap: 4rem;
		align-items: center;
	}

	@media (min-width: 1024px) {
		.about-grid {
			grid-template-columns: 1.1fr 1.3fr;
			gap: 5rem;
		}
	}

	/* Image column with tilted frame */
	.about-image-col {
		display: flex;
		justify-content: center;
	}

	.image-tilt-frame {
		width: 100%;
		max-width: 380px;
		aspect-ratio: 0.9;
		border-radius: var(--border-radius-lg);
		background: #ffffff;
		border: 1px solid rgba(0, 0, 0, 0.08);
		box-shadow: 0 15px 40px rgba(0, 0, 0, 0.05);
		transform: rotate(-3deg);
		transition: var(--transition-smooth);
		overflow: hidden;
	}

	.image-tilt-frame:hover {
		transform: rotate(0) scale(1.02);
		border-color: var(--color-accent-dim);
		box-shadow: 0 25px 50px rgba(157, 255, 59, 0.15);
	}

	.about-img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		filter: grayscale(100%);
		transition: var(--transition-smooth);
	}

	.image-tilt-frame:hover .about-img {
		filter: grayscale(0%);
	}

	/* Content Column */
	.section-tag {
		color: var(--color-accent-dim);
		font-size: 1.1rem;
		display: block;
		margin-bottom: 0.5rem;
	}

	.about-title {
		font-size: clamp(2.2rem, 4.5vw, 4.5rem);
		font-weight: 700;
		line-height: 0.95;
		color: var(--color-text-primary);
		letter-spacing: -1.5px;
		margin-bottom: 2rem;
	}

	.font-light {
		font-weight: 300;
	}

	.about-bio {
		display: flex;
		flex-direction: column;
		gap: 1.25rem;
		color: var(--color-text-secondary);
		font-size: 1rem;
		line-height: 1.7;
		margin-bottom: 2.5rem;
	}

	/* Details table layout */
	.details-table {
		display: flex;
		flex-direction: column;
		border-top: 1px solid rgba(0, 0, 0, 0.06);
		margin-bottom: 2.5rem;
	}

	.details-row {
		display: flex;
		justify-content: space-between;
		padding-block: 1rem;
		border-bottom: 1px solid rgba(0, 0, 0, 0.06);
		gap: 2rem;
		align-items: center;
	}

	.detail-label {
		font-size: 0.85rem;
		font-weight: 700;
		text-transform: uppercase;
		letter-spacing: 1px;
		color: var(--color-text-muted);
		flex-shrink: 0;
	}

	.detail-value {
		font-size: 0.95rem;
		font-weight: 600;
		color: var(--color-text-primary);
		text-align: right;
	}

	/* Social connections */
	.social-links-row {
		display: flex;
		gap: 1rem;
	}

	.social-link {
		width: 3rem;
		height: 3rem;
		border-radius: 50%;
		background: rgba(0, 0, 0, 0.02);
		border: 1px solid rgba(0, 0, 0, 0.06);
		display: flex;
		align-items: center;
		justify-content: center;
		color: var(--color-text-secondary);
		transition: var(--transition-medium);
	}

	.social-link:hover {
		background: var(--color-accent);
		color: #000;
		border-color: var(--color-accent-dim);
		transform: translateY(-2px);
		box-shadow: 0 8px 25px rgba(157, 255, 59, 0.35);
	}
</style>
