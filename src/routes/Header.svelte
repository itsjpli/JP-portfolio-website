<script>
	import { page } from '$app/state';
</script>

<div class="header-container">
	<header>
		<div class="left">
			<a href="/" class="logo">
				<img src="/signature.svg" alt="JP Li" />
			</a>
		</div>

		<nav class="center">
			<a href="/" class="nav-link" class:active={page.url.pathname === '/'}>Data</a>
			<a href="/feature-writing" class="nav-link" class:active={page.url.pathname === '/feature-writing'}>Feature</a>
			<a href="/about" class="nav-link" class:active={page.url.pathname === '/about'}>About</a>
		</nav>

		<div class="right">
			<a href="https://theabacus.substack.com/" target="_blank" rel="noopener noreferrer" class="newsletter-btn">Join my newsletter</a>
		</div>
	</header>
</div>

<style>
	.header-container {
		width: 100%;
	}

	header {
		width: 90%;
		height: 70px;
		background-color: #F9F4ED;
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 0 2rem;
		margin: 0.5rem auto 0;
		border-radius: 12px;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
	}

	.left,
	.center,
	.right {
		flex: 1;
		display: flex;
		align-items: center;
	}

	.left {
		justify-content: flex-start;
	}

	.center {
		justify-content: center;
		gap: 2rem;
	}

	.right {
		justify-content: flex-end;
	}

	.logo {
		display: flex;
		align-items: center;
		text-decoration: none;
		transition: opacity 0.2s ease;
	}

	.logo img {
		height: 40px;
		width: auto;
	}

	.logo:hover {
		opacity: 0.7;
	}

	.nav-link {
		font-size: 0.95rem;
		font-family: var(--font-heading);
		color: #333;
		text-decoration: none;
		padding-bottom: 2px;
		position: relative;
		transition: color 0.2s ease;
		white-space: nowrap;
	}

	.nav-link::after {
		content: '';
		position: absolute;
		bottom: 0;
		left: 0;
		width: 0;
		height: 1.5px;
		background-color: #333;
		transition: width 0.3s ease;
	}

	.nav-link:hover::after {
		width: 100%;
	}

	.nav-link.active::after {
		width: 100%;
	}

	.newsletter-btn {
		padding: 0.5rem 1rem;
		font-size: 0.85rem;
		font-family: var(--font-heading);
		color: #333;
		text-decoration: none;
		border: 1.5px solid #333;
		border-radius: 8px;
		transition: all 0.2s ease;
		white-space: nowrap;
	}

	.newsletter-btn:hover {
		background-color: #F85C03;
		color: #ffffff;
		border-color: #F85C03;
	}

</style>
