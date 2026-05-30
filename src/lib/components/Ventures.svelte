<script lang="ts">
	// Interactive ventures metrics for Light Mode
	const metrics = [
		{ value: '$40M+', label: 'Cumulative Impact' },
		{ value: '5+', label: 'Companies Built' },
		{ value: '15+', label: 'Years Experience' },
		{ value: '3+', label: 'Fintech Products' }
	];
</script>

<section class="ventures-section" id="ventures">
	<div class="container">
		<div class="section-header">
			<span class="section-tag text-serif italic">/ Portfolio Spotlight</span>
			<h2 class="section-title text-sans">Selected <span class="text-serif italic font-light">Ventures</span></h2>
		</div>

		<!-- Major Showcase Container (glowing light neon frame) -->
		<div class="showcase-outer-frame">
			<div class="showcase-header">
				<div class="window-dots">
					<span class="dot red"></span>
					<span class="dot yellow"></span>
					<span class="dot green"></span>
				</div>
				<span class="window-title text-sans">DAVID'S VENTURES IMPACT MAP</span>
			</div>
			
			<div class="showcase-grid">
				<!-- Zoodlabs Dashboard Mockup -->
				<div class="glass-card venture-card zoodlabs-card">
					<div class="venture-badge">CONNECTIVITY & INFRASTRUCTURE</div>
					<h3 class="venture-name text-sans"><span class="text-serif italic font-light">01</span> Zoodlabs</h3>
					<p class="venture-desc">Co-founded and scaled Sierra Leone's premier broadband infrastructure provider, deploying subsea fiber integrations and solar-powered smart towers.</p>
					
					<!-- Mini Interactive Dashboard Mockup -->
					<div class="dashboard-mockup">
						<div class="dash-row">
							<span class="dash-label">Fiber Network Capacity</span>
							<span class="dash-value text-accent">100 Gbps</span>
						</div>
						<div class="progress-bar">
							<div class="progress-fill" style="width: 82%"></div>
						</div>
						<div class="dash-chart">
							<svg viewBox="0 0 100 30" class="chart-svg">
								<path d="M0,25 Q15,5 30,20 T60,10 T90,15 L100,5 L100,30 L0,30 Z" fill="rgba(157,255,59,0.15)" stroke="var(--color-accent-dim)" stroke-width="1.5" />
							</svg>
						</div>
					</div>
				</div>

				<!-- Rasab Group / Flot Mobile UI Mockup -->
				<div class="glass-card venture-card flot-card">
					<div class="venture-badge">FINTECH & PAYMENTS</div>
					<h3 class="venture-name text-sans"><span class="text-serif italic font-light">02</span> OpenHub & Rasab Group</h3>
					<p class="venture-desc">Fintech systems scaled by David: OpenHub drives the Flot merchant aggregator platform, while Rasab Group anchors VultPay utility rails and agent networks.</p>
					
					<!-- Mini Mobile Phone Mockup -->
					<div class="phone-mockup">
						<div class="phone-screen">
							<div class="phone-header">
								<span class="time">09:41</span>
								<span class="signal">
									<svg width="14" height="8" viewBox="0 0 24 12" fill="none" stroke="currentColor" stroke-width="2" style="opacity: 0.8; display: inline-block; vertical-align: middle;">
										<rect x="1" y="1" width="18" height="10" rx="2" />
										<path d="M20 4v4" stroke-linecap="round" />
										<rect x="3" y="3" width="11" height="6" rx="1" fill="currentColor" />
									</svg>
								</span>
							</div>
							<div class="balance-card">
								<span class="bal-lbl">VultPay Balance</span>
								<span class="bal-val">Le 4,500.00</span>
							</div>
							<div class="tx-list">
								<div class="tx-item">
									<span class="tx-name">Flot Merchant</span>
									<span class="tx-amount text-accent">+Le 250.00</span>
								</div>
								<div class="tx-item">
									<span class="tx-name">Cash Out</span>
									<span class="tx-amount">-Le 100.00</span>
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Metro Cable Card -->
				<div class="glass-card venture-card metro-card">
					<div class="venture-badge">METROPOLITAN FIBER</div>
					<h3 class="venture-name text-sans"><span class="text-serif italic font-light">03</span> Metro Cable</h3>
					<p class="venture-desc">Laying metro fiber grids to connect corporate nodes, state operations, and residential portals into a unified digital speedway.</p>
					<div class="grid-stats">
						<span class="stat-num text-accent">500+ KM</span>
						<span class="stat-lbl">Fiber Laid</span>
					</div>
				</div>

				<!-- Chapi Core Tech -->
				<div class="glass-card venture-card chapi-card">
					<div class="venture-badge">SOFTWARE LAB</div>
					<h3 class="venture-name text-sans"><span class="text-serif italic font-light">04</span> Chapi Core Tech</h3>
					<p class="venture-desc">Custom enterprise solutions, big data analytics, and digital transformations tailored to banking and telecom systems.</p>
					<div class="grid-stats">
						<span class="stat-num text-accent">12+</span>
						<span class="stat-lbl">Enterprise Apps</span>
					</div>
				</div>
			</div>
			
			<!-- Bottom Tagline inside the frame -->
			<div class="frame-footer">
				<p class="frame-tag text-serif italic">Seen Recent Impact</p>
			</div>
		</div>

		<!-- Metrics Grid below -->
		<div class="metrics-grid">
			{#each metrics as metric}
				<div class="metric-card glass-card">
					<span class="metric-value text-serif text-accent">{metric.value}</span>
					<span class="metric-label text-sans">{metric.label}</span>
				</div>
			{/each}
		</div>
	</div>
</section>

<style>
	.ventures-section {
		position: relative;
		background-color: var(--color-bg);
	}

	.section-header {
		margin-bottom: 3rem;
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

	/* Showcase frame light design matching mockup */
	.showcase-outer-frame {
		background: #ffffff;
		border: 1px solid rgba(0, 0, 0, 0.06);
		border-top: 4px solid var(--color-accent-dim);
		border-radius: 16px;
		padding: 2.5rem;
		position: relative;
		box-shadow: 0 15px 45px rgba(0, 0, 0, 0.025), inset 0 1px 0 rgba(255, 255, 255, 0.8);
	}

	.showcase-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		border-bottom: 1px solid rgba(0, 0, 0, 0.05);
		padding-bottom: 1.5rem;
		margin-bottom: 2rem;
	}

	.window-dots {
		display: flex;
		gap: 6px;
	}

	.dot {
		width: 8px;
		height: 8px;
		border-radius: 50%;
		background: rgba(0, 0, 0, 0.1);
		transition: var(--transition-medium);
	}

	.showcase-outer-frame:hover .dot.red { background: #ff5f56; }
	.showcase-outer-frame:hover .dot.yellow { background: #ffbd2e; }
	.showcase-outer-frame:hover .dot.green { background: #27c93f; }

	.window-title {
		font-size: 0.75rem;
		font-weight: 700;
		letter-spacing: 2px;
		color: var(--color-text-muted);
	}

	.showcase-grid {
		display: grid;
		grid-template-columns: 1fr;
		gap: 1.5rem;
	}

	@media (min-width: 768px) {
		.showcase-grid {
			grid-template-columns: 1fr 1fr;
		}
	}

	/* Venture Cards */
	.venture-card {
		padding: 2.25rem;
		display: flex;
		flex-direction: column;
		min-height: 280px;
		background: #ffffff;
		border: 1px solid rgba(0, 0, 0, 0.05);
	}

	.venture-badge {
		font-size: 0.7rem;
		font-weight: 800;
		letter-spacing: 1.5px;
		color: var(--color-accent-dim);
		margin-bottom: 1rem;
		text-transform: uppercase;
	}

	.venture-name {
		font-size: 1.8rem;
		font-weight: 700;
		margin-bottom: 0.75rem;
		color: var(--color-text-primary);
		letter-spacing: -0.5px;
	}

	.venture-desc {
		font-size: 0.95rem;
		color: var(--color-text-secondary);
		line-height: 1.5;
		margin-bottom: 1.5rem;
	}

	/* Dashboard Mockup Light styling */
	.dashboard-mockup {
		background: #f7f9f6;
		border: 1px solid rgba(0, 0, 0, 0.05);
		border-radius: var(--border-radius-sm);
		padding: 1rem;
		margin-top: auto;
	}

	.dash-row {
		display: flex;
		justify-content: space-between;
		font-size: 0.75rem;
		margin-bottom: 0.5rem;
	}

	.dash-label {
		color: var(--color-text-muted);
	}

	.dash-value {
		font-weight: 700;
	}

	.progress-bar {
		height: 4px;
		background: rgba(0, 0, 0, 0.05);
		border-radius: var(--border-radius-pill);
		overflow: hidden;
		margin-bottom: 0.75rem;
	}

	.progress-fill {
		height: 100%;
		background: var(--color-accent-dim);
		box-shadow: 0 0 5px rgba(157, 255, 59, 0.5);
	}

	.chart-svg {
		width: 100%;
		height: 40px;
	}

	/* Phone Mockup iOS light styling */
	.phone-mockup {
		width: 170px;
		height: 240px;
		background: #ffffff;
		border: 6px solid #1c2117;
		border-radius: 24px;
		margin-top: auto;
		align-self: center;
		position: relative;
		overflow: hidden;
		box-shadow: 0 12px 35px rgba(0, 0, 0, 0.06);
	}

	.phone-mockup::before {
		content: '';
		position: absolute;
		top: 0;
		left: 50%;
		transform: translateX(-50%);
		width: 65px;
		height: 10px;
		background: #1c2117;
		border-bottom-left-radius: 6px;
		border-bottom-right-radius: 6px;
		z-index: 10;
	}

	.phone-screen {
		display: flex;
		flex-direction: column;
		padding: 0.75rem;
		height: 100%;
		font-size: 0.65rem;
		background: #f7f9f6;
	}

	.phone-header {
		display: flex;
		justify-content: space-between;
		color: var(--color-text-muted);
		margin-bottom: 1rem;
		font-weight: 700;
	}

	.balance-card {
		background: #ffffff;
		border: 1px solid rgba(0, 0, 0, 0.04);
		border-radius: 8px;
		padding: 0.5rem;
		text-align: center;
		margin-bottom: 1rem;
	}

	.bal-lbl {
		color: var(--color-text-muted);
		display: block;
		font-size: 0.55rem;
	}

	.bal-val {
		font-weight: 800;
		font-size: 0.85rem;
		color: var(--color-text-primary);
	}

	.tx-list {
		display: flex;
		flex-direction: column;
		gap: 0.4rem;
	}

	.tx-item {
		display: flex;
		justify-content: space-between;
		border-bottom: 1px solid rgba(0,0,0,0.03);
		padding-bottom: 0.2rem;
	}

	.tx-name {
		color: var(--color-text-secondary);
	}

	/* Stats Layout Cards */
	.grid-stats {
		margin-top: auto;
		display: flex;
		flex-direction: column;
	}

	.stat-num {
		font-size: 2.2rem;
		font-weight: 700;
		font-family: var(--font-serif);
		line-height: 1;
	}

	.stat-lbl {
		font-size: 0.75rem;
		color: var(--color-text-muted);
		text-transform: uppercase;
		letter-spacing: 1px;
	}

	.frame-footer {
		margin-top: 2rem;
		text-align: right;
		border-top: 1px solid rgba(0, 0, 0, 0.06);
		padding-top: 1.5rem;
	}

	.frame-tag {
		font-size: 1.5rem;
		color: var(--color-text-primary);
	}

	/* Bottom Metrics Grid */
	.metrics-grid {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 1rem;
		margin-top: 3rem;
	}

	@media (min-width: 1024px) {
		.metrics-grid {
			grid-template-columns: repeat(4, 1fr);
			gap: 1.5rem;
		}
	}

	.metric-card {
		padding: 2rem;
		display: flex;
		flex-direction: column;
		align-items: center;
		text-align: center;
		background: #ffffff;
		border: 1px solid rgba(0, 0, 0, 0.04);
	}

	.metric-value {
		font-size: clamp(2.5rem, 4vw, 4rem);
		line-height: 1;
		font-weight: 700;
		margin-bottom: 0.5rem;
	}

	.metric-label {
		font-size: 0.85rem;
		color: var(--color-text-secondary);
		font-weight: 500;
	}
</style>
