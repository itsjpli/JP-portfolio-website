<script>
	import Header from './Header.svelte';
	import '../app.css';

	/** @type {{children: import('svelte').Snippet}} */
	let { children } = $props();
</script>

<div class="app">
	<Header />

	<main>
		{@render children()}
	</main>

	<footer>
		<div class="footer-divider"></div>
		<div class="footer-content">
			<div class="footer-left">
				<p>© 2025 Jinpeng Li</p>
			</div>
			<div class="footer-right">
				<a href="mailto:forjpli@gmail.com" class="social-icon" aria-label="Email">
					<svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
						<rect x="2" y="4" width="20" height="16" rx="2"/>
						<path d="m2 7 10 7 10-7"/>
					</svg>
				</a>
				<a href="https://github.com/itsjpli" target="_blank" rel="noopener noreferrer" class="social-icon" aria-label="GitHub">
					<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
						<path d="M12 2C6.477 2 2 6.477 2 12c0 4.42 2.865 8.17 6.839 9.49.5.092.682-.217.682-.482 0-.237-.008-.866-.013-1.7-2.782.603-3.369-1.34-3.369-1.34-.454-1.156-1.11-1.463-1.11-1.463-.908-.62.069-.608.069-.608 1.003.07 1.531 1.03 1.531 1.03.892 1.529 2.341 1.087 2.91.831.092-.646.35-1.086.636-1.336-2.22-.253-4.555-1.11-4.555-4.943 0-1.091.39-1.984 1.029-2.683-.103-.253-.446-1.27.098-2.647 0 0 .84-.269 2.75 1.025A9.578 9.578 0 0112 6.836c.85.004 1.705.114 2.504.336 1.909-1.294 2.747-1.025 2.747-1.025.546 1.377.203 2.394.1 2.647.64.699 1.028 1.592 1.028 2.683 0 3.842-2.339 4.687-4.566 4.935.359.309.678.919.678 1.852 0 1.336-.012 2.415-.012 2.743 0 .267.18.578.688.48C19.138 20.167 22 16.418 22 12c0-5.523-4.477-10-10-10z"/>
					</svg>
				</a>
				<a href="https://bsky.app/profile/itsjpli.bsky.social" class="social-icon" aria-label="Bluesky">
					<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
						<path d="M12 10.8c-1.087-2.114-4.046-6.053-6.798-7.995C2.566.944 1.561 1.266.902 1.565.139 1.908 0 3.08 0 3.768c0 .69.378 5.65.624 6.479.815 2.736 3.713 3.66 6.383 3.364.136-.02.275-.039.415-.056-.138.022-.276.04-.415.056-3.912.58-7.387 2.005-2.83 7.078 5.013 5.19 6.87-1.113 7.823-4.308.953 3.195 2.05 9.271 7.733 4.308 4.267-4.308 1.172-6.498-2.74-7.078a8.741 8.741 0 01-.415-.056c.14.017.279.036.415.056 2.67.297 5.568-.628 6.383-3.364.246-.828.624-5.79.624-6.478 0-.69-.139-1.861-.902-2.206-.659-.298-1.664-.62-4.3 1.24C16.046 4.748 13.087 8.687 12 10.8z"/>
					</svg>
				</a>
				<a href="https://www.linkedin.com/in/itsrealjp/" target="_blank" rel="noopener noreferrer" class="social-icon" aria-label="LinkedIn">
					<svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
						<path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
					</svg>
				</a>
			</div>
		</div>
	</footer>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 0;
		width: 80%;
		margin: 2rem auto 0;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		width: 90%;
		margin: 2rem auto;
		padding: 0;
	}

	.footer-divider {
		width: 100%;
		height: 1px;
		background-color: #e5e7eb;
		margin-bottom: 1.5rem;
	}

	.footer-content {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.footer-left p {
		margin: 0;
		font-size: 0.9rem;
		font-family: var(--font-heading);
		color: #6b7280;
	}

	.footer-right {
		display: flex;
		gap: 1.5rem;
		align-items: center;
	}

	.social-icon {
		color: #6b7280;
		transition: color 0.2s ease;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.social-icon:hover {
		color: #111827;
	}

	@media (min-width: 480px) {
		footer {
			width: 90%;
		}
	}
</style>
