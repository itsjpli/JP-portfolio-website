<script>
	import { page } from '$app/state';

	let { onDropdownChange = () => {} } = $props();

	let dropdownOpen = $state(false);

	function toggleDropdown() {
		dropdownOpen = !dropdownOpen;
		onDropdownChange(dropdownOpen);
	}

	function closeDropdown() {
		dropdownOpen = false;
		onDropdownChange(false);
	}
</script>

<div class="header-container">
	<header>
		<div class="left">
			<a href="/" class="logo">
				<img src="/signature.svg" alt="JP Li" />
			</a>
		</div>

		<nav class="center">
			<div class="nav-item-wrapper">
				<button class="nav-link work-dropdown" onclick={toggleDropdown}>
					Work
					<svg class="chevron" class:rotated={dropdownOpen} width="12" height="12" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg">
						<path d="M3 4.5L6 7.5L9 4.5" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
					</svg>
				</button>
				{#if dropdownOpen}
					<div class="dropdown-menu">
						<a href="/" class="dropdown-link" onclick={closeDropdown}>Data Journalism</a>
						<a href="/feature-writing" class="dropdown-link" onclick={closeDropdown}>Feature Writing</a>
					</div>
				{/if}
			</div>
			<a href="/about" class="nav-link">About</a>
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
		gap: 2.5rem;
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

	.nav-item-wrapper {
		position: relative;
	}

	.nav-link {
		font-size: 1rem;
		font-family: var(--font-heading);
		color: #333;
		text-decoration: none;
		transition: all 0.2s ease;
		position: relative;
		background: none;
		border: none;
		cursor: pointer;
		padding: 0;
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

	.work-dropdown {
		display: flex;
		align-items: center;
		gap: 0.3rem;
	}

	.chevron {
		transition: transform 0.3s ease;
		display: inline-flex;
		margin-left: 0.25rem;
	}

	.chevron.rotated {
		transform: rotate(180deg);
	}

	.dropdown-menu {
		position: absolute;
		left: 50%;
		transform: translateX(-50%);
		top: calc(100% + 12px);
		width: auto;
		min-width: 180px;
		background-color: #F9F4ED;
		border-radius: 8px;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
		padding: 0.5rem;
		display: flex;
		flex-direction: column;
		gap: 0;
		z-index: 1000;
	}

	.dropdown-link {
		padding: 0.5rem 1rem;
		font-size: 0.9rem;
		font-family: var(--font-heading);
		color: #333;
		text-decoration: none;
		transition: all 0.2s ease;
		border-radius: 8px;
		font-weight: 500;
	}

	.dropdown-link:hover {
		background-color: #EDE8DC;
		color: #111827;
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
