<script>
	import recentWork from '$lib/data/feature-writing.json';
</script>

<svelte:head>
	<title>Feature Writing - JP Li</title>
</svelte:head>

<div class="container">
	<div class="hero">
		<p class="hero-label-small">I write human-driven narratives,</p>
		<p class="hero-label">covering US politics, tech, and business</p>
	</div>

	<div class="stories-grid">
		{#each recentWork as work}
			<div class="story-card">
				<div class="story-image">
					<img src={work.image} alt={work.titleChinese} />
				</div>
				<div class="story-body">
					<div class="story-meta">
						<span class="story-publication">{work.publication}</span>
						<span class="story-date">{work.date}</span>
					</div>
					<h2 class="story-title">{work.titleChinese} <span class="story-title-english">{work.titleEnglish}</span></h2>
					{#if work.description}
						<div class="story-links">{@html work.description}</div>
					{/if}
				</div>
			</div>
		{/each}
	</div>
</div>

<style>
	.container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 2rem 0 4rem 0;
	}

	/* Hero */
	.hero {
		text-align: left;
		margin-bottom: 6rem;
		max-width: 450px;
		padding-top: 2rem;
	}

	.hero-label-small {
		font-size: 1rem;
		font-family: var(--font-heading);
		font-weight: 500;
		color: #111827;
		letter-spacing: 0;
		line-height: 1.4;
		margin: 0 0 0.5rem 0;
	}

	.hero-label {
		font-size: 2.5rem;
		font-family: var(--font-heading);
		font-weight: 700;
		color: #111827;
		letter-spacing: -0.02em;
		line-height: 1.2;
		margin: 0 0 2.5rem 0;
	}

	.tagline {
		font-size: 0.875rem;
		font-family: var(--font-body);
		color: #9ca3af;
		line-height: 1.9;
		margin: 0;
	}

	.tagline a {
		color: #374151;
		text-decoration: underline;
		text-underline-offset: 3px;
	}

	.tagline a:hover {
		color: #F85C03;
	}

	/* Grid */
	.stories-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 2.5rem 2rem;
	}

	.story-card {
		display: flex;
		flex-direction: column;
	}

	.story-image {
		width: 100%;
		aspect-ratio: 16 / 10;
		overflow: hidden;
		border-radius: 8px;
		background: #f3f4f6;
		margin-bottom: 0.875rem;
	}

	.story-image img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		transition: transform 0.3s ease;
	}

	.story-card:hover .story-image img {
		transform: scale(1.03);
	}

	.story-body {
		display: flex;
		flex-direction: column;
		gap: 0.3rem;
	}

	.story-meta {
		display: flex;
		gap: 0.6rem;
		align-items: center;
	}

	.story-publication {
		font-size: 0.72rem;
		font-family: var(--font-heading);
		font-weight: 600;
		color: #F85C03;
		text-transform: uppercase;
		letter-spacing: 0.06em;
	}

	.story-date {
		font-size: 0.72rem;
		font-family: var(--font-heading);
		color: #9ca3af;
	}

	.story-title {
		font-size: 1rem;
		font-family: 'SimSun', '宋体', serif;
		color: #111827;
		margin: 0;
		line-height: 1.6;
		font-weight: 400;
	}

	.story-title-english {
		font-size: 0.85rem;
		font-family: var(--font-heading);
		color: #6b7280;
		margin: 0.2rem 0 0 0;
		line-height: 1.4;
		font-weight: 400;
	}

	.story-links {
		font-size: 0.82rem;
		font-family: var(--font-heading);
		line-height: 1.8;
		margin-top: 0.1rem;
	}

	.story-links :global(strong) {
		display: none;
	}

	.story-links :global(a) {
		color: #6b7280;
		text-decoration: none;
		display: block;
		line-height: 1.5;
	}

	.story-links :global(a:hover) {
		color: #111827;
		text-decoration: underline;
		text-underline-offset: 2px;
	}

	.story-links :global(br) {
		display: none;
	}

	/* Mobile */
	@media (max-width: 768px) {
		.hero {
			margin-bottom: 3rem;
			padding-top: 1rem;
		}

		.tagline {
			font-size: 0.95rem;
		}

		.stories-grid {
			grid-template-columns: 1fr;
			gap: 2.5rem;
		}
	}

	@media (min-width: 769px) and (max-width: 1024px) {
		.stories-grid {
			grid-template-columns: repeat(2, 1fr);
		}
	}
</style>
