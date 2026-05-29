<footer class="footer">
	<div class="container">
		<div class="footer-top-row">
			<!-- Links Navigation -->
			<nav class="footer-nav text-sans">
				<a href="#home" class="footer-link">Home</a>
				<a href="#about" class="footer-link">Biography</a>
				<a href="#ventures" class="footer-link">Ventures</a>
				<a href="#timeline" class="footer-link">Timeline</a>
				<a href="#news" class="footer-link">News & Media</a>
				<a href="#contact" class="footer-link">Contact</a>
			</nav>

			<!-- Copyright & Disclaimers -->
			<div class="footer-meta text-sans text-muted">
				<p>© 2026 David Kpakima. All rights reserved.</p>
				<p class="disclaimer">All data sourced from verified public announcements, company registries, and press reports.</p>
			</div>
		</div>

		<!-- Massive Footer Display Text replicating mockup in Light Mode -->
		<div class="footer-big-text-wrapper">
			<h2 class="footer-big-name text-serif italic">David Kpakima</h2>
		</div>
	</div>
</footer>

<style>
	.footer {
		border-top: 1px solid rgba(0, 0, 0, 0.05);
		padding-top: 4rem;
		padding-bottom: 2rem;
		background: #ffffff;
		position: relative;
		overflow: hidden;
	}

	.footer-top-row {
		display: flex;
		flex-direction: column;
		gap: 2.5rem;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 5rem;
		position: relative;
		z-index: 10;
	}

	@media (min-width: 768px) {
		.footer-top-row {
			flex-direction: row;
			align-items: flex-start;
		}
	}

	/* Footer Nav Links */
	.footer-nav {
		display: flex;
		flex-wrap: wrap;
		gap: 1.5rem 2rem;
		justify-content: center;
	}

	@media (min-width: 768px) {
		.footer-nav {
			justify-content: flex-start;
		}
	}

	.footer-link {
		font-size: 0.95rem;
		font-weight: 600;
		color: var(--color-text-secondary);
		transition: var(--transition-quick);
		position: relative;
	}

	.footer-link::after {
		content: '';
		position: absolute;
		bottom: -4px;
		left: 0;
		width: 0%;
		height: 1.5px;
		background: var(--color-accent-dim);
		transition: var(--transition-quick);
	}

	.footer-link:hover {
		color: var(--color-accent-dim);
	}

	.footer-link:hover::after {
		width: 100%;
	}

	/* Footer Meta Copyright */
	.footer-meta {
		font-size: 0.8rem;
		text-align: center;
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
		max-width: 320px;
	}

	@media (min-width: 768px) {
		.footer-meta {
			text-align: right;
		}
	}

	.disclaimer {
		font-size: 0.7rem;
		opacity: 0.5;
	}

	/* Giant Display Name footer */
	.footer-big-text-wrapper {
		width: 100%;
		overflow: hidden;
		display: flex;
		justify-content: center;
		margin-top: 2rem;
		position: relative;
		z-index: 1;
	}

	.footer-big-name {
		font-size: clamp(4.5rem, 16vw, 15rem);
		font-weight: 300;
		line-height: 0.8;
		letter-spacing: -5px;
		text-align: center;
		white-space: nowrap;
		user-select: none;
		pointer-events: none;
		background: linear-gradient(to bottom, rgba(15, 19, 11, 0.05) 0%, rgba(15, 19, 11, 0.01) 100%);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}
</style>
