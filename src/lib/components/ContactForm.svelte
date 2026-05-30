<script lang="ts">
	let showModal = $state(false);
	let isSubmitting = $state(false);
	let isSuccess = $state(false);

	let name = $state('');
	let email = $state('');
	let company = $state('');
	let message = $state('');

	function openModal() {
		showModal = true;
		document.body.style.overflow = 'hidden';
	}

	function closeModal() {
		showModal = false;
		document.body.style.overflow = '';
		isSuccess = false;
	}

	async function handleSubmit(e: SubmitEvent) {
		e.preventDefault();
		if (!name || !email || !message) return;

		isSubmitting = true;
		
		// Simulate network API request
		await new Promise(resolve => setTimeout(resolve, 1500));
		
		isSubmitting = false;
		isSuccess = true;

		// Clear form
		name = '';
		email = '';
		company = '';
		message = '';
	}
</script>

<section class="contact-section" id="contact">
	<div class="container">
		<!-- Large Glowing Neon CTA Card matching mockup -->
		<div class="cta-banner">
			<div class="cta-content">
				<h2 class="cta-title text-sans">Let's Work <span class="text-serif italic font-light">Together</span></h2>
				<p class="cta-subtext text-sans">
					Always open to hearing about new infrastructure projects, tech ventures, speaking engagements, or discussing partnerships.
				</p>
			</div>
			<button class="cta-btn text-sans" onclick={openModal}>
				Get in touch
			</button>
		</div>
	</div>
</section>

<!-- Popover/Modal Dialog for Contact Form -->
{#if showModal}
	<!-- svelte-ignore a11y_click_events_have_key_events -->
	<!-- svelte-ignore a11y_no_static_element_interactions -->
	<div class="contact-modal-backdrop" onclick={closeModal}>
		<!-- svelte-ignore a11y_click_events_have_key_events -->
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<div class="contact-modal glass-card" onclick={(e) => e.stopPropagation()}>
			<button class="modal-close" onclick={closeModal} aria-label="Close modal">&times;</button>
			
			<div class="modal-header">
				<span class="modal-tag text-serif italic">Let's Connect</span>
				<h3 class="modal-title text-sans">Inquire & Partner</h3>
			</div>

			{#if isSuccess}
				<div class="success-view text-sans">
					<div class="success-icon">✓</div>
					<h4 class="success-title">Message Sent!</h4>
					<p class="success-text text-muted">
						Thank you for reaching out. David's executive assistant will review your query and get back to you shortly.
					</p>
					<button class="btn-primary" onclick={closeModal}>Done</button>
				</div>
			{:else}
				<form class="contact-form text-sans" onsubmit={handleSubmit}>
					<div class="form-group">
						<label for="name" class="form-label">Full Name *</label>
						<input 
							type="text" 
							id="name" 
							bind:value={name} 
							required 
							placeholder="John Doe" 
							class="form-input" 
						/>
					</div>

					<div class="form-group">
						<label for="email" class="form-label">Email Address *</label>
						<input 
							type="email" 
							id="email" 
							bind:value={email} 
							required 
							placeholder="john@example.com" 
							class="form-input" 
						/>
					</div>

					<div class="form-group">
						<label for="company" class="form-label">Company / Organization</label>
						<input 
							type="text" 
							id="company" 
							bind:value={company} 
							placeholder="Acme Corp" 
							class="form-input" 
						/>
					</div>

					<div class="form-group">
						<label for="message" class="form-label">Message *</label>
						<textarea 
							id="message" 
							bind:value={message} 
							required 
							rows="4" 
							placeholder="Tell me about your project, speaking event, or inquiry..." 
							class="form-textarea"
						></textarea>
					</div>

					<div class="form-footer">
						<button type="submit" class="btn-primary submit-btn" disabled={isSubmitting}>
							{#if isSubmitting}
								<span>Sending...</span>
							{:else}
								<span>Send Message</span>
								<svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
									<line x1="22" y1="2" x2="11" y2="13"></line>
									<polygon points="22 2 15 22 11 13 2 9 22 2"></polygon>
								</svg>
							{/if}
						</button>
					</div>
				</form>
			{/if}
		</div>
	</div>
{/if}

<style>
	.contact-section {
		padding-block: var(--spacing-lg);
		background-color: var(--color-bg);
	}

	/* Glowing neon banner design matching mockup */
	.cta-banner {
		background: linear-gradient(135deg, var(--color-accent) 0%, #d8ff8c 100%);
		border-radius: var(--border-radius-lg);
		padding: 3.5rem 2.5rem;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		gap: 2.5rem;
		box-shadow: 0 20px 40px rgba(157, 255, 59, 0.2);
		text-align: center;
	}

	@media (min-width: 768px) {
		.cta-banner {
			flex-direction: row;
			text-align: left;
			padding: 4.5rem;
		}
	}

	.cta-content {
		max-width: 600px;
	}

	.cta-title {
		font-size: clamp(2rem, 3.5vw, 3.5rem);
		font-weight: 700;
		color: #000;
		line-height: 1;
		margin-bottom: 1rem;
		letter-spacing: -1.5px;
	}

	.cta-subtext {
		font-size: 1.05rem;
		color: rgba(0, 0, 0, 0.7);
		line-height: 1.5;
		font-weight: 500;
	}

	.cta-btn {
		background: #000;
		color: #fff;
		border: none;
		padding: 1.1rem 2.2rem;
		border-radius: var(--border-radius-pill);
		font-size: 1rem;
		font-weight: 600;
		cursor: pointer;
		transition: var(--transition-medium);
		box-shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
		flex-shrink: 0;
	}

	.cta-btn:hover {
		background: #1a1a1a;
		transform: translateY(-3px);
		box-shadow: 0 15px 40px rgba(0, 0, 0, 0.35);
	}

	/* Modal Backdrop Styling */
	.contact-modal-backdrop {
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

	.contact-modal {
		width: 100%;
		max-width: 550px;
		background: #ffffff;
		padding: 3rem;
		position: relative;
		box-shadow: 0 40px 80px rgba(0, 0, 0, 0.15);
		border-color: rgba(157, 255, 59, 0.3);
		animation: modalOpen 0.4s cubic-bezier(0.16, 1, 0.3, 1) forwards;
	}

	@keyframes modalOpen {
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
		font-size: 2.2rem;
		font-weight: 700;
		color: var(--color-text-primary);
		letter-spacing: -0.5px;
	}

	/* Form Inputs Styling */
	.contact-form {
		display: flex;
		flex-direction: column;
		gap: 1.25rem;
	}

	.form-group {
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	.form-label {
		font-size: 0.75rem;
		font-weight: 700;
		color: var(--color-text-secondary);
		text-transform: uppercase;
		letter-spacing: 0.8px;
	}

	.form-input, .form-textarea {
		background: rgba(0, 0, 0, 0.02);
		border: 1px solid rgba(0, 0, 0, 0.08);
		border-radius: var(--border-radius-sm);
		padding: 0.85rem 1.1rem;
		color: var(--color-text-primary);
		font-size: 0.95rem;
		transition: var(--transition-medium);
	}

	.form-input:focus, .form-textarea:focus {
		outline: none;
		border-color: var(--color-accent-dim);
		background: rgba(157, 255, 59, 0.03);
		box-shadow: 0 0 10px rgba(157, 255, 59, 0.1);
	}

	.form-textarea {
		resize: vertical;
	}

	.form-footer {
		margin-top: 1.5rem;
		display: flex;
		justify-content: flex-end;
	}

	.submit-btn {
		width: 100%;
		justify-content: center;
	}

	@media (min-width: 640px) {
		.submit-btn {
			width: auto;
		}
	}

	.submit-btn:disabled {
		opacity: 0.5;
		cursor: not-allowed;
	}

	/* Success View */
	.success-view {
		text-align: center;
		padding: 2rem 1rem;
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 1.5rem;
	}

	.success-icon {
		width: 4rem;
		height: 4rem;
		border-radius: 50%;
		background: rgba(157, 255, 59, 0.1);
		border: 2px solid var(--color-accent-dim);
		color: var(--color-accent-dim);
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 1.8rem;
		font-weight: 700;
	}

	.success-title {
		font-size: 1.8rem;
		font-weight: 700;
		color: var(--color-text-primary);
	}

	.success-text {
		font-size: 0.95rem;
		line-height: 1.6;
		color: var(--color-text-secondary);
		max-width: 320px;
	}
</style>
