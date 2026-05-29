<script lang="ts">
	// Interactive News and statement items for Light Mode
	let activeStatement = $state(false);

	function openStatement(e: MouseEvent) {
		e.preventDefault();
		activeStatement = true;
	}

	function closeStatement() {
		activeStatement = false;
	}
</script>

<svelte:window onkeydown={(e) => { if (e.key === 'Escape' && activeStatement) closeStatement(); }} />

<section class="news-section" id="news">
	<div class="container">
		<div class="section-header">
			<span class="section-tag text-serif italic">/ Media Feed</span>
			<h2 class="section-title text-sans">News & Transparency</h2>
		</div>

		<!-- Replicating the Selected Works Grid with Visual Mockup Headers -->
		<div class="news-grid">
			
			<!-- Card 1: Zenith Rec Fair -->
			<div class="glass-card news-card">
				<!-- Mockup Header representing Selected Works screenshot -->
				<div class="card-visual-header header-green">
					<div class="presentation-slide">
						<div class="slide-nav">
							<span class="slide-dot"></span>
							<span class="slide-title">ZENITH FORUM • KEYNOTE</span>
						</div>
						<div class="slide-content-view">
							<h4 class="slide-large-text text-serif">Building Sierra Leone's Digital Talent Ecosystem</h4>
							<span class="slide-sub">DAVID KPAKIMA • 2025 ADDRESS</span>
						</div>
					</div>
				</div>

				<div class="card-meta">
					<div class="glass-icon" style="--pill-accent: #2eb82e">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
							<path d="M12 2a3 3 0 0 0-3 3v7a3 3 0 0 0 6 0V5a3 3 0 0 0-3-3Z" fill="currentColor" fill-opacity="0.1" />
							<path d="M19 10v1a7 7 0 0 1-14 0v-1" />
							<line x1="12" y1="19" x2="12" y2="22" />
						</svg>
					</div>
					<span class="news-type text-sans">Speaking Engagement</span>
				</div>
				
				<div class="card-content">
					<h3 class="news-title text-sans">Zenith Rec Fair Keynote 2025</h3>
					<p class="news-desc">Delivered the keynote on how fintech and broadband infrastructure are unlocking jobs and engineering careers in Sierra Leone.</p>
				</div>

				<div class="card-footer">
					<div class="tag-row">
						<span class="news-tag">Speaking</span>
						<span class="news-tag">Fintech</span>
					</div>
					<a href="https://linkedin.com" class="news-link text-sans text-accent" target="_blank" rel="noopener noreferrer">
						<span>Watch Session</span>
						<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
							<line x1="7" y1="17" x2="17" y2="7"></line>
							<polyline points="7 7 17 7 17 17"></polyline>
						</svg>
					</a>
				</div>
			</div>

			<!-- Card 2: JAB Show Video -->
			<div class="glass-card news-card">
				<!-- Mockup Header representing video player screenshot -->
				<div class="card-visual-header header-yellow">
					<div class="video-player-mockup">
						<div class="podcast-visual">
							<span class="pod-tag text-sans">THE JAB SHOW</span>
							<h4 class="pod-title text-serif">Startup Blueprint: Scale in West Africa</h4>
							<!-- Audio wave visualizer -->
							<div class="audio-wave">
								<span class="wave-bar" style="height: 35%"></span>
								<span class="wave-bar" style="height: 60%"></span>
								<span class="wave-bar" style="height: 85%"></span>
								<span class="wave-bar" style="height: 45%"></span>
								<span class="wave-bar" style="height: 75%"></span>
								<span class="wave-bar" style="height: 55%"></span>
								<span class="wave-bar" style="height: 90%"></span>
								<span class="wave-bar" style="height: 40%"></span>
							</div>
						</div>
						<div class="play-btn-circle">
							<svg viewBox="0 0 24 24" fill="currentColor" class="play-svg">
								<polygon points="5 3 19 12 5 21 5 3"></polygon>
							</svg>
						</div>
					</div>
				</div>

				<div class="card-meta">
					<div class="glass-icon" style="--pill-accent: #e6b800">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
							<rect x="2" y="2" width="20" height="20" rx="2.18" ry="2.18" />
							<line x1="7" y1="2" x2="7" y2="22" />
							<line x1="17" y1="2" x2="17" y2="22" />
							<line x1="2" y1="12" x2="22" y2="12" />
						</svg>
					</div>
					<span class="news-type text-sans">Video Interview</span>
				</div>
				
				<div class="card-content">
					<h3 class="news-title text-sans">The JAB Show: Startup Blueprint</h3>
					<p class="news-desc">A comprehensive interview discussing the realities of building multi-million dollar tech infrastructure startups in West Africa.</p>
				</div>

				<div class="card-footer">
					<div class="tag-row">
						<span class="news-tag">Video</span>
						<span class="news-tag">Entrepreneurship</span>
					</div>
					<a href="https://linkedin.com" class="news-link text-sans text-accent" target="_blank" rel="noopener noreferrer">
						<span>Watch Interview</span>
						<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
							<line x1="7" y1="17" x2="17" y2="7"></line>
							<polyline points="7 7 17 7 17 17"></polyline>
						</svg>
					</a>
				</div>
			</div>

			<!-- Card 3: Insights Article -->
			<div class="glass-card news-card">
				<!-- Mockup Header representing document screenshot -->
				<div class="card-visual-header header-blue">
					<div class="article-mockup">
						<span class="article-category text-sans">INFRASTRUCTURE INSIGHTS</span>
						<h4 class="article-title text-serif">Closing the Digital Divide: Local Subsea and Terrestrial Infrastructure</h4>
						<p class="article-excerpt">Why localized ownership of core telecom and payments assets represents the single greatest growth lever in the global south...</p>
						<span class="article-author text-sans">BY DAVID KPAKIMA • 4 MIN READ</span>
					</div>
				</div>

				<div class="card-meta">
					<div class="glass-icon" style="--pill-accent: #3399ff">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
							<path d="M14.5 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V7.5L14.5 2z" />
							<polyline points="14 2 14 8 20 8" />
							<line x1="16" y1="13" x2="8" y2="13" />
							<line x1="16" y1="17" x2="8" y2="17" />
						</svg>
					</div>
					<span class="news-type text-sans">Article / Insights</span>
				</div>
				
				<div class="card-content">
					<h3 class="news-title text-sans">Africa's Broadband Leap</h3>
					<p class="news-desc">Published piece on why local ownership of digital infrastructure is the key to closing the digital divide in the global south.</p>
				</div>

				<div class="card-footer">
					<div class="tag-row">
						<span class="news-tag">Insights</span>
						<span class="news-tag">Broadband</span>
					</div>
					<a href="https://linkedin.com" class="news-link text-sans text-accent" target="_blank" rel="noopener noreferrer">
						<span>Read Article</span>
						<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
							<line x1="7" y1="17" x2="17" y2="7"></line>
							<polyline points="7 7 17 7 17 17"></polyline>
						</svg>
					</a>
				</div>
			</div>

			<!-- Card 4: Transparency Gavel Statement -->
			<div class="glass-card news-card legal-accent">
				<!-- Mockup Header representing corporate balance sheet / court statement -->
				<div class="card-visual-header header-red">
					<div class="court-seal-mockup">
						<div class="court-header">
							<span class="court-name text-sans">IN THE HIGH COURT OF SIERRA LEONE</span>
							<span class="court-matter text-serif">In the Matter of Zoodlabs & Metro Cable Commercial Leadership</span>
						</div>
						<div class="court-seal-emblem">
							<svg viewBox="0 0 24 24" fill="currentColor" class="seal-svg">
								<circle cx="12" cy="12" r="10" fill="none" stroke="currentColor" stroke-width="1.5" />
								<circle cx="12" cy="12" r="8" fill="none" stroke="currentColor" stroke-width="1" stroke-dasharray="2 1" />
								<path d="M12 6v12 M8 10h8 M6 14c0-2 2-2 2-2s2 0 2 2 M14 14c0-2 2-2 2-2s2 0 2 2" fill="none" stroke="currentColor" stroke-width="1.25"/>
							</svg>
							<span class="seal-certified text-sans">OFFICIAL RULING PROTECTIVE ORDER 2026</span>
						</div>
					</div>
				</div>

				<div class="card-meta">
					<div class="glass-icon" style="--pill-accent: #ff5c33">
						<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
							<path d="M16 16v1a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V7a2 2 0 0 1 2-2h11a2 2 0 0 1 2 2v1" />
							<path d="M18 8h4a2 2 0 0 1 2 2v7a2 2 0 0 1-2 2h-4" />
							<circle cx="11" cy="12" r="3" fill="currentColor" fill-opacity="0.1" />
						</svg>
					</div>
					<span class="news-type text-sans">Legal & Transparency</span>
				</div>
				
				<div class="card-content">
					<h3 class="news-title text-sans">Zoodlabs & Metro Cable Statement</h3>
					<p class="news-desc">Addressing the 2025 Zoodlabs dispute: David strongly denied the Global Times allegations of mismanagement, leading to 2026 High Court protective orders.</p>
				</div>

				<div class="card-footer">
					<div class="tag-row">
						<span class="news-tag">Corporate</span>
						<span class="news-tag">Statement</span>
					</div>
					<a href="#statement" class="news-link text-sans text-accent" onclick={openStatement}>
						<span>Read Legal Summary</span>
						<svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
							<line x1="7" y1="17" x2="17" y2="7"></line>
							<polyline points="7 7 17 7 17 17"></polyline>
						</svg>
					</a>
				</div>
			</div>

		</div>
	</div>
</section>
<!-- Modal Overlay for the Transparency Statement -->
{#if activeStatement}
	<!-- svelte-ignore a11y_click_events_have_key_events -->
	<!-- svelte-ignore a11y_no_static_element_interactions -->
	<div class="statement-modal-backdrop" onclick={closeStatement}>
		<!-- svelte-ignore a11y_click_events_have_key_events -->
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<div class="statement-modal glass-card" onclick={(e) => e.stopPropagation()}>
			<button class="modal-close" onclick={closeStatement} aria-label="Close modal">&times;</button>
			
			<div class="modal-header">
				<span class="modal-tag text-serif italic">Legal Statement & Context</span>
				<h3 class="modal-title text-sans">Zoodlabs & Metro Cable Statement</h3>
			</div>

			<div class="modal-body text-sans">
				<p>
					<strong>Overview of 2025 Dispute:</strong> In mid-2025, public allegations and media publications (primarily carried by the Global Times) raised questions of fraud, embezzlement, and operational mismanagement concerning the leadership of Zoodlabs and Metro Cable during David Kpakima’s tenure as executive director/CEO.
				</p>
				<p>
					<strong>Denials & Actions:</strong> David Tamba Abdulai Kpakima strongly and categorically denied all allegations of wrongdoing, pointing to audit trails, operational metrics, and the presence of external investment audits confirming the integrity of the project funds. In response, he initiated legal actions for defamation and sought judicial intervention to protect commercial reputation.
				</p>
				<p>
					<strong>High Court Rulings (2026):</strong> In early 2026, the disputes reached the High Court. The High Court issued interim and protective orders in David Kpakima’s favor, freezing adverse claims, restraining malicious publications, and validating his commercial leadership rights pending full resolution.
				</p>
				<blockquote>
					"This website frames these corporate events factually and transparently, demonstrating our commitment to corporate governance, transparency, and the rule of law."
				</blockquote>
			</div>

			<div class="modal-footer">
				<button class="btn-primary" onclick={closeStatement}>Close Statement</button>
			</div>
		</div>
	</div>
{/if}

<style>
	.news-section {
		position: relative;
		background-color: var(--color-section-alt);
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
		margin-bottom: 4rem;
	}

	/* Grid layout matching mockup */
	.news-grid {
		display: grid;
		grid-template-columns: 1fr;
		gap: 2rem;
	}

	@media (min-width: 768px) {
		.news-grid {
			grid-template-columns: repeat(2, 1fr);
		}
	}

	.news-card {
		display: flex;
		flex-direction: column;
		background: #ffffff;
		border: 1px solid rgba(0, 0, 0, 0.05);
		box-shadow: 0 4px 20px rgba(0, 0, 0, 0.02);
		transition: var(--transition-smooth);
		overflow: hidden;
		border-radius: var(--border-radius-lg);
	}

	.news-card:hover {
		transform: translateY(-5px);
		border-color: var(--color-accent-dim);
		box-shadow: 0 20px 40px rgba(157, 255, 59, 0.12);
	}

	/* Highlights controversies professionally */
	.news-card.legal-accent {
		border-color: rgba(255, 107, 74, 0.3);
	}
	.news-card.legal-accent:hover {
		border-color: rgba(255, 107, 74, 0.8);
		box-shadow: 0 20px 40px rgba(255, 107, 74, 0.08);
	}

	/* Visual Mockup Header representing Selected Works screenshots */
	.card-visual-header {
		height: 180px;
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 1.5rem;
		position: relative;
		overflow: hidden;
		border-bottom: 1px solid rgba(0, 0, 0, 0.04);
	}

	.header-green { background: linear-gradient(135deg, rgba(46, 184, 46, 0.05) 0%, rgba(46, 184, 46, 0.01) 100%); }
	.header-yellow { background: linear-gradient(135deg, rgba(230, 184, 0, 0.05) 0%, rgba(230, 184, 0, 0.01) 100%); }
	.header-blue { background: linear-gradient(135deg, rgba(51, 153, 255, 0.05) 0%, rgba(51, 153, 255, 0.01) 100%); }
	.header-red { background: linear-gradient(135deg, rgba(255, 92, 51, 0.05) 0%, rgba(255, 92, 51, 0.01) 100%); }

	/* Presentation slide mockup details */
	.presentation-slide {
		width: 100%;
		height: 100%;
		background: linear-gradient(135deg, #1c2117 0%, #0d100b 100%);
		border: 1px solid rgba(255, 255, 255, 0.08);
		border-radius: 8px;
		box-shadow: 0 4px 20px rgba(0, 0, 0, 0.15);
		padding: 1rem;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}

	.slide-nav {
		display: flex;
		align-items: center;
		gap: 0.5rem;
	}

	.slide-dot {
		width: 6px;
		height: 6px;
		background: var(--color-accent-dim);
		border-radius: 50%;
		box-shadow: 0 0 6px var(--color-accent);
	}

	.slide-title {
		font-size: 0.5rem;
		font-weight: 800;
		color: rgba(255, 255, 255, 0.4);
		letter-spacing: 1px;
	}

	.slide-content-view {
		display: flex;
		flex-direction: column;
		gap: 0.25rem;
		text-align: left;
		margin-top: 0.5rem;
	}

	.slide-large-text {
		font-size: 0.85rem;
		font-weight: 400;
		color: #ffffff;
		line-height: 1.3;
		letter-spacing: -0.2px;
	}

	.slide-sub {
		font-size: 0.48rem;
		font-weight: 700;
		color: var(--color-accent-dim);
		letter-spacing: 0.8px;
	}

	/* Video player mockup details */
	.video-player-mockup {
		width: 100%;
		height: 100%;
		background: #090b07;
		border-radius: 8px;
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 1rem;
		position: relative;
		overflow: hidden;
	}

	.podcast-visual {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		max-width: 70%;
		text-align: left;
	}

	.pod-tag {
		font-size: 0.5rem;
		font-weight: 800;
		color: var(--color-accent-dim);
		letter-spacing: 1px;
	}

	.pod-title {
		font-size: 0.8rem;
		font-weight: 400;
		color: #ffffff;
		line-height: 1.3;
		margin-top: 0.25rem;
	}

	.audio-wave {
		display: flex;
		align-items: center;
		gap: 3px;
		height: 24px;
		margin-top: 0.5rem;
	}

	.wave-bar {
		width: 3px;
		background: rgba(223, 177, 91, 0.7); /* gold aesthetic */
		border-radius: 1.5px;
		animation: pulse-wave 1.5s ease-in-out infinite alternate;
	}

	/* Subtle audio wave pulses */
	.wave-bar:nth-child(2) { animation-delay: 0.2s; }
	.wave-bar:nth-child(3) { animation-delay: 0.4s; }
	.wave-bar:nth-child(4) { animation-delay: 0.1s; }
	.wave-bar:nth-child(5) { animation-delay: 0.3s; }
	.wave-bar:nth-child(6) { animation-delay: 0.5s; }
	.wave-bar:nth-child(7) { animation-delay: 0.2s; }
	.wave-bar:nth-child(8) { animation-delay: 0.4s; }

	@keyframes pulse-wave {
		0% { transform: scaleY(0.5); }
		100% { transform: scaleY(1.1); }
	}

	.play-btn-circle {
		width: 2.5rem;
		height: 2.5rem;
		border-radius: 50%;
		background: rgba(255, 255, 255, 0.1);
		backdrop-filter: blur(4px);
		display: flex;
		align-items: center;
		justify-content: center;
		color: #ffffff;
		border: 1px solid rgba(255, 255, 255, 0.25);
		box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
		transition: all 0.3s ease;
	}

	.video-player-mockup:hover .play-btn-circle {
		transform: scale(1.08);
		background: var(--color-accent);
		color: #000000;
		border-color: var(--color-accent);
		box-shadow: 0 0 15px rgba(157, 255, 59, 0.4);
	}

	.play-svg {
		width: 1rem;
		height: 1rem;
		margin-left: 2px;
	}

	/* Article layout mockup details */
	.article-mockup {
		width: 100%;
		height: 100%;
		background: #ffffff;
		border: 1px solid rgba(0, 0, 0, 0.05);
		border-radius: 8px;
		padding: 1rem;
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		text-align: left;
		box-shadow: 0 4px 15px rgba(0, 0, 0, 0.015);
	}

	.article-category {
		font-size: 0.5rem;
		font-weight: 800;
		color: #3399ff;
		letter-spacing: 1px;
		line-height: 1;
	}

	.article-title {
		font-size: 0.72rem;
		font-weight: 700;
		color: var(--color-text-primary);
		line-height: 1.25;
		margin-top: 0.25rem;
	}

	.article-excerpt {
		font-size: 0.58rem;
		color: var(--color-text-secondary);
		line-height: 1.4;
		margin-top: 0.25rem;
		opacity: 0.85;
	}

	.article-author {
		font-size: 0.45rem;
		font-weight: 800;
		color: var(--color-text-muted);
		letter-spacing: 0.5px;
		margin-top: auto;
	}

	/* Court seal mockup details */
	.court-seal-mockup {
		width: 100%;
		height: 100%;
		border: 1.5px solid rgba(223, 177, 91, 0.25);
		border-radius: 8px;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 0.75rem 1rem;
		gap: 0.5rem;
		background: #FAF8F5; /* warm legal paper shade */
		box-shadow: inset 0 0 10px rgba(223, 177, 91, 0.05);
	}

	.court-header {
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
	}

	.court-name {
		font-size: 0.48rem;
		font-weight: 800;
		color: var(--color-text-primary);
		letter-spacing: 0.8px;
	}

	.court-matter {
		font-size: 0.6rem;
		font-style: italic;
		color: var(--color-text-secondary);
		margin-top: 0.15rem;
		line-height: 1.2;
	}

	.court-seal-emblem {
		display: flex;
		align-items: center;
		justify-content: center;
		gap: 0.4rem;
		color: #DFB15B;
		margin-top: 0.25rem;
	}

	.seal-svg {
		width: 1.25rem;
		height: 1.25rem;
		flex-shrink: 0;
	}

	.seal-certified {
		font-size: 0.45rem;
		font-weight: 800;
		color: var(--color-text-primary);
		letter-spacing: 0.5px;
	}

	/* Card Metadata spacing */
	.card-meta {
		padding: 1.5rem 2rem 0;
		display: flex;
		align-items: center;
		gap: 0.75rem;
	}

	.news-type {
		font-size: 0.75rem;
		font-weight: 700;
		text-transform: uppercase;
		letter-spacing: 1px;
		color: var(--color-text-muted);
	}

	/* Card Content */
	.card-content {
		padding: 1rem 2rem 1.5rem;
		flex-grow: 1;
	}

	.news-title {
		font-size: 1.4rem;
		font-weight: 700;
		margin-bottom: 0.75rem;
		color: var(--color-text-primary);
		line-height: 1.2;
	}

	.news-desc {
		font-size: 0.95rem;
		color: var(--color-text-secondary);
		line-height: 1.6;
	}

	/* Card Footer */
	.card-footer {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-top: auto;
		border-top: 1px solid rgba(0, 0, 0, 0.05);
		padding: 1.5rem 2rem 2rem;
	}

	.tag-row {
		display: flex;
		gap: 0.5rem;
	}

	.news-tag {
		font-size: 0.7rem;
		background: rgba(0, 0, 0, 0.03);
		padding: 0.25rem 0.6rem;
		border-radius: var(--border-radius-pill);
		color: var(--color-text-secondary);
		border: 1px solid rgba(0, 0, 0, 0.04);
	}

	.news-link {
		display: flex;
		align-items: center;
		gap: 0.5rem;
		font-size: 0.85rem;
		font-weight: 600;
	}

	.news-link svg {
		transition: transform 0.3s var(--transition-medium);
	}

	.news-link:hover svg {
		transform: translate(2px, -2px);
	}

	/* Modal Styling */
	.statement-modal-backdrop {
		position: fixed;
		top: 0;
		left: 0;
		width: 100vw;
		height: 100vh;
		background: rgba(15, 20, 10, 0.45);
		backdrop-filter: blur(12px);
		z-index: 2000;
		display: flex;
		justify-content: center;
		align-items: center;
		padding: 1.5rem;
	}

	.statement-modal {
		width: 100%;
		max-width: 650px;
		background: #ffffff;
		padding: 3rem;
		position: relative;
		box-shadow: 0 40px 80px rgba(0, 0, 0, 0.15);
		border-color: rgba(157, 255, 59, 0.3);
		animation: modalFadeIn 0.4s cubic-bezier(0.16, 1, 0.3, 1) forwards;
	}

	@keyframes modalFadeIn {
		from {
			opacity: 0;
			transform: scale(0.95) translateY(10px);
		}
		to {
			opacity: 1;
			transform: scale(1) translateY(0);
		}
	}

	.modal-close {
		position: absolute;
		top: 1.5rem;
		right: 1.5rem;
		background: none;
		border: none;
		color: var(--color-text-muted);
		font-size: 2rem;
		cursor: pointer;
		line-height: 1;
		transition: color 0.2s ease;
	}

	.modal-close:hover {
		color: var(--color-accent-dim);
	}

	.modal-header {
		margin-bottom: 2rem;
	}

	.modal-tag {
		color: var(--color-accent-dim);
		font-size: 1.1rem;
		display: block;
		margin-bottom: 0.5rem;
	}

	.modal-title {
		font-size: clamp(1.8rem, 3vw, 2.5rem);
		font-weight: 700;
		color: var(--color-text-primary);
		letter-spacing: -0.5px;
	}

	.modal-body {
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
		color: var(--color-text-secondary);
		font-size: 0.95rem;
		line-height: 1.7;
	}

	blockquote {
		border-left: 3px solid var(--color-accent-dim);
		padding-left: 1.5rem;
		margin-block: 1rem;
		font-style: italic;
		color: var(--color-text-primary);
	}

	.modal-footer {
		margin-top: 2.5rem;
		display: flex;
		justify-content: flex-end;
	}
</style>
