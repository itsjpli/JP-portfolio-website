<script>
	import { page } from '$app/state';
</script>

<header>
	<div class="left">
		<a href="/" class="logo">"JP" Li</a>
	</div>

	<nav class="center">
		<a href="/" class="nav-link">Work</a>
		<a href="/about" class="nav-link">About</a>
	</nav>

	<div class="right">
		<a href="https://theabacus.substack.com/" target="_blank" rel="noopener noreferrer" class="newsletter-btn">Join my newsletter</a>
	</div>
</header>

<style>
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
		gap: 2.5rem;
	}

	.right {
		justify-content: flex-end;
	}

	.logo {
		font-size: 1.75rem;
		font-weight: 700;
		font-family: 'Rufina', var(--font-heading);
		color: #1a1a1a;
		text-decoration: none;
		transition: opacity 0.2s ease;
	}

	.logo:hover {
		opacity: 0.7;
	}

	.nav-link {
		font-size: 1rem;
		font-family: var(--font-heading);
		color: #333;
		text-decoration: none;
		transition: all 0.2s ease;
		position: relative;
	}

	.nav-link:hover {
		color: #000;
	}

	.nav-link::after {
		content: '';
		position: absolute;
		bottom: -4px;
		left: 0;
		width: 0;
		height: 2px;
		background-color: #333;
		transition: width 0.2s ease;
	}

	.nav-link:hover::after {
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
