<script lang="ts">
	// Timeline milestones
	const steps = [
		{
			num: '01',
			title: 'Corporate Foundations',
			desc: 'Led client experience, brand, and marketing at Zain, Airtel, and Standard Chartered Bank, building deep telecommunications and retail banking foundations.'
		},
		{
			num: '02',
			title: 'Infrastructure Leadership',
			desc: 'Served as Chief Commercial Officer at SALCAB (Sierra Leone Cable), managing subsea fiber optic operations and expanding national broadband commercialization.'
		},
		{
			num: '03',
			title: 'Venture Building (2019+)',
			desc: 'Co-founded Zoodlabs (broadband, 5G towers) and Rasab Group (Fintech, Flot, VultPay), scaling digital ecosystems with over $40M in cumulative economic impact.'
		}
	];

	// Testimonials data with avatars for Light Mode
	const testimonials = [
		{
			quote: "David's vision for digital infrastructure transformed how we thought about connectivity. He bridges the gap between commercial strategy and native engineering with absolute ease.",
			author: "Davar Fazaeli",
			role: "Co-Founder at Zoodlabs",
			avatarColor: '#d8ff8c'
		},
		{
			quote: "Partnering with Rasab Group on payment rails unlocked financial accessibility for thousands of local merchants. David is a relentless execution-focused C-suite leader.",
			author: "Alhassan Kamara",
			role: "Director of Payments Ecosystems",
			avatarColor: '#d8ff8c'
		}
	];
</script>

<section class="timeline-section" id="timeline">
	<div class="container">
		<div class="section-header">
			<span class="section-tag text-serif italic">/ Career Journey</span>
			<h2 class="section-title text-sans">Professional <span class="text-serif italic font-light">Milestones</span></h2>
		</div>

		<!-- Cards Container with Dotted Curly SVG Line -->
		<div class="timeline-wrapper">
			<!-- SVG Path connector replicating the hand-drawn loops in mockup -->
			<div class="svg-line-container">
				<svg viewBox="0 0 1000 300" fill="none" preserveAspectRatio="none" class="connecting-line-svg">
					<!-- Double loop path -->
					<path 
						d="M 100 150 C 250 80, 220 220, 280 220 C 340 220, 380 40, 480 120 C 580 200, 620 40, 680 150 C 740 260, 780 150, 900 150" 
						stroke="rgba(127, 207, 44, 0.4)" 
						stroke-width="2.5" 
						stroke-linecap="round"
						stroke-dasharray="6 5"
					/>
					<!-- Curly arrow flourishes -->
					<path d="M 275 210 Q 280 220 285 210" stroke="var(--color-accent-dim)" stroke-width="2"/>
					<path d="M 675 140 Q 680 150 685 140" stroke="var(--color-accent-dim)" stroke-width="2"/>
					<circle cx="100" cy="150" r="5" fill="var(--color-accent-dim)" />
					<circle cx="480" cy="120" r="5" fill="var(--color-accent-dim)" />
					<circle cx="900" cy="150" r="5" fill="var(--color-accent-dim)" />
				</svg>
			</div>

			<div class="timeline-grid">
				{#each steps as step}
					<div class="glass-card timeline-card card-{step.num}">
						<span class="step-num text-serif">{step.num}</span>
						<h3 class="step-title text-sans">{step.title}</h3>
						<p class="step-desc">{step.desc}</p>
					</div>
				{/each}
			</div>
		</div>

		<!-- Testimonials Grid below timeline -->
		<div class="testimonials-grid">
			{#each testimonials as item}
				<div class="glass-card testimonial-card">
					<span class="quote-mark">“</span>
					<p class="quote-text text-sans">{item.quote}</p>
					<div class="quote-footer">
						<!-- Custom SVG Profile Avatar inside a glass ring -->
						<div class="author-avatar" style="--avatar-bg: {item.avatarColor}">
							<svg viewBox="0 0 32 32" fill="none" stroke="currentColor" stroke-width="2">
								<path d="M16 18a6 6 0 1 0 0-12 6 6 0 0 0 0 12ZM6 26a10 10 0 0 1 20 0" fill="currentColor" fill-opacity="0.15" />
							</svg>
						</div>
						<div class="quote-author">
							<span class="author-name text-sans">{item.author}</span>
							<span class="author-role text-muted">{item.role}</span>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<style>
	.timeline-section {
		position: relative;
		overflow: hidden;
		background-color: var(--color-bg);
	}

	.section-tag {
		color: var(--color-accent-dim);
		font-size: 1.1rem;
		display: block;
		margin-bottom: 0.5rem;
	}

	.section-title {
		font-size: clamp(2rem, 4vw, 3.5rem);
		font-weight: 700;
		letter-spacing: -1px;
	}

	/* Timeline Cards & SVG line */
	.timeline-wrapper {
		position: relative;
		margin-top: 4rem;
		padding-bottom: 2rem;
	}

	.svg-line-container {
		display: none;
	}

	@media (min-width: 1024px) {
		.svg-line-container {
			display: block;
			position: absolute;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			pointer-events: none;
			z-index: 1;
		}
		.connecting-line-svg {
			width: 100%;
			height: 100%;
		}
	}

	.timeline-grid {
		display: grid;
		grid-template-columns: 1fr;
		gap: 2rem;
		position: relative;
		z-index: 2;
	}

	@media (min-width: 1024px) {
		.timeline-grid {
			grid-template-columns: repeat(3, 1fr);
			gap: 3rem;
		}
	}

	.timeline-card {
		padding: 2.5rem;
		min-height: 280px;
		display: flex;
		flex-direction: column;
		background: #ffffff;
		border: 1px solid rgba(0, 0, 0, 0.05);
		box-shadow: 0 4px 20px rgba(0, 0, 0, 0.02);
		transition: var(--transition-smooth);
	}

	@media (min-width: 1024px) {
		.card-01 {
			transform: translateY(20px);
		}
		.card-02 {
			transform: translateY(-20px);
		}
		.card-03 {
			transform: translateY(10px);
		}

		.timeline-card:hover {
			transform: translateY(0) scale(1.03);
			border-color: var(--color-accent-dim);
			box-shadow: 0 20px 40px rgba(157, 255, 59, 0.12);
		}
	}

	.step-num {
		font-size: 3.5rem;
		font-weight: 700;
		color: var(--color-accent-dim);
		opacity: 0.25;
		line-height: 1;
		margin-bottom: 1rem;
		transition: var(--transition-medium);
	}

	.timeline-card:hover .step-num {
		opacity: 0.85;
		transform: scale(1.1);
	}

	.step-title {
		font-size: 1.4rem;
		font-weight: 700;
		margin-bottom: 1rem;
		color: var(--color-text-primary);
	}

	.step-desc {
		font-size: 0.95rem;
		color: var(--color-text-secondary);
		line-height: 1.6;
	}

	/* Testimonials styling */
	.testimonials-grid {
		display: grid;
		grid-template-columns: 1fr;
		gap: 1.5rem;
		margin-top: 5rem;
	}

	@media (min-width: 768px) {
		.testimonials-grid {
			grid-template-columns: 1fr 1fr;
			gap: 2rem;
		}
	}

	.testimonial-card {
		padding: 2.5rem;
		position: relative;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		background: #ffffff;
		border: 1px solid rgba(15, 19, 11, 0.06);
		border-radius: var(--border-radius-lg);
		box-shadow: 
			0 4px 15px rgba(0, 0, 0, 0.01),
			0 12px 30px rgba(0, 0, 0, 0.02),
			4px 4px 0px rgba(157, 255, 59, 0.1),
			8px 8px 0px rgba(157, 255, 59, 0.05);
		transition: var(--transition-smooth);
		transform: translateY(0) translate(0, 0);
	}

	.testimonial-card:hover {
		transform: translateY(-4px) translate(-2px, -2px);
		box-shadow: 
			0 8px 25px rgba(0, 0, 0, 0.02),
			0 20px 45px rgba(0, 0, 0, 0.04),
			6px 6px 0px rgba(157, 255, 59, 0.15),
			12px 12px 0px rgba(157, 255, 59, 0.08);
	}

	.quote-mark {
		font-family: var(--font-serif);
		font-size: 4rem;
		color: var(--color-accent-dim);
		line-height: 0.1;
		position: absolute;
		top: 1.5rem;
		left: 1.5rem;
		opacity: 0.25;
	}

	.quote-text {
		font-size: 1rem;
		color: var(--color-text-secondary);
		line-height: 1.6;
		margin-bottom: 2rem;
		position: relative;
		z-index: 2;
	}

	.quote-footer {
		display: flex;
		align-items: center;
		gap: 1rem;
		margin-top: auto;
		border-top: 1px solid rgba(0, 0, 0, 0.04);
		padding-top: 1.25rem;
	}

	.author-avatar {
		width: 2.5rem;
		height: 2.5rem;
		border-radius: 50%;
		background: var(--avatar-bg);
		border: 1px solid rgba(0, 0, 0, 0.08);
		display: flex;
		align-items: center;
		justify-content: center;
		color: var(--color-text-primary);
		box-shadow: 0 4px 10px rgba(0, 0, 0, 0.03);
	}

	.author-avatar svg {
		width: 1.25rem;
		height: 1.25rem;
	}

	.quote-author {
		display: flex;
		flex-direction: column;
	}

	.author-name {
		font-weight: 700;
		font-size: 0.9rem;
		color: var(--color-text-primary);
	}

	.author-role {
		font-size: 0.75rem;
	}
</style>
