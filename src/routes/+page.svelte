<script>
	import projectsData from '$lib/data/projects.json';

	let projects = projectsData;
	let categories = ['All', 'Business', 'Sports', 'Investigation'];
	let selectedCategory = 'All';
	let selectedType = 'Interactives';
	let featuredProject = projects[0]; // First item = highest ID = newest
	let hoveredProject = projects[1] || projects[0]; // Start with second project, or first if only one

	$: filteredProjects = selectedCategory === 'All'
		? projects
		: projects.filter(p => p.category === selectedCategory);

	$: interactiveProjects = filteredProjects.filter(p => p.type === 'Interactives');
	$: dataReportingProjects = filteredProjects.filter(p => p.type === 'Data Reporting');

	$: displayedProjects = selectedType === 'Interactives' ? interactiveProjects : dataReportingProjects;

	function selectCategory(category) {
		selectedCategory = category;
		hoveredProject = displayedProjects[0] || null;
	}

	function selectType(type) {
		selectedType = type;
		hoveredProject = type === 'Data Graphics' ? interactiveProjects[0] : dataReportingProjects[0];
	}

	function handleHover(project) {
		hoveredProject = project;
	}
</script>

<svelte:head>
	<title>Interactives</title>
	<meta name="description" content="Interactive project showcase" />
</svelte:head>

<div class="container">
	<!-- Featured Project Section -->
	<section class="featured-section">
		<div class="featured-image">
			<img src={featuredProject.thumbnail} alt={featuredProject.title} />
		</div>
		<div class="featured-content">
			<div class="featured-badges">
				<span class="latest-badge">Latest</span>
				<span class="featured-category">{featuredProject.category}</span>
			</div>
			<div class="featured-meta">
				<span class="featured-publication">{featuredProject.publication_name}</span>
				<span class="featured-date">{new Date(featuredProject.date).toLocaleDateString('en-US', { month: 'short', year: 'numeric' })}</span>
			</div>
			<h1 class="featured-title">
				<a href={featuredProject.url} target="_blank" rel="noopener noreferrer" class="featured-title-link">
					{featuredProject.title}
				</a>
			</h1>
			<p class="featured-description">{featuredProject.description}</p>
		</div>
	</section>

	<div class="main-layout">
		<!-- Project List with Sticky Labels -->
		<div class="project-list-container">
			<!-- Category Navigation -->
			<nav class="nav-bar">
				{#each categories as category}
					<button
						class="nav-item"
						class:active={selectedCategory === category}
						on:click={() => selectCategory(category)}
					>
						{category}
					</button>
				{/each}
			</nav>

			<!-- Type Navigation (Mobile Only) -->
			<nav class="type-nav-mobile">
				<button
					class="type-nav-item"
					class:active={selectedType === 'Interactives'}
					on:click={() => selectType('Interactives')}
				>
					Interactives
				</button>
				<button
					class="type-nav-item"
					class:active={selectedType === 'Data Reporting'}
					on:click={() => selectType('Data Reporting')}
				>
					Data Reporting
				</button>
			</nav>

			<!-- Scrollable Sections Container -->
			<div class="sections-container">
				<!-- Data Graphics Section -->
				{#if interactiveProjects.length > 0}
					<div class="project-section" class:mobile-hidden={selectedType !== 'Interactives'}>
						<div class="sticky-label-wrapper">
							<button
								class="sticky-label data-graphics"
								class:active={selectedType === 'Interactives'}
								on:click={() => selectType('Interactives')}
							>
								<span class="label-text">Interactives</span>
							</button>
						</div>
						<div class="project-list">
							{#each interactiveProjects as project (project.id)}
								<div
									class="project-item"
									class:hovered={hoveredProject?.id === project.id}
									on:mouseenter={() => handleHover(project)}
									role="button"
									tabindex="0"
								>
									<div class="project-info">
										<span class="project-title">{project.title}</span>
										<span class="project-publication">{project.publication_name}</span>
									</div>
								</div>
							{/each}
						</div>
					</div>
				{/if}

				<!-- Data Reporting Section -->
				{#if dataReportingProjects.length > 0}
					<div class="project-section" class:mobile-hidden={selectedType !== 'Data Reporting'}>
						<div class="sticky-label-wrapper">
							<button
								class="sticky-label data-reporting"
								class:active={selectedType === 'Data Reporting'}
								on:click={() => selectType('Data Reporting')}
							>
								<span class="label-text">Data Reporting</span>
							</button>
						</div>
						<div class="project-list">
							{#each dataReportingProjects as project (project.id)}
								<div
									class="project-item"
									class:hovered={hoveredProject?.id === project.id}
									on:mouseenter={() => handleHover(project)}
									role="button"
									tabindex="0"
								>
									<div class="project-info">
										<span class="project-title">{project.title}</span>
										<span class="project-publication">{project.publication_name}</span>
									</div>
								</div>
							{/each}
						</div>
					</div>
				{/if}
			</div>
		</div>

		<!-- Project Detail View -->
		<div class="project-detail">
			{#if hoveredProject}
				<div class="detail-visualization">
					<img src={hoveredProject.thumbnail} alt={hoveredProject.title} />
				</div>

				<div class="detail-header">
					<div class="detail-meta">
						<span class="detail-category">{hoveredProject.category}</span>
						<span class="detail-date">{new Date(hoveredProject.date).toLocaleDateString('en-US', { month: 'short', year: 'numeric' })}</span>
					</div>
					<h1 class="detail-title">
						<a href={hoveredProject.url} target="_blank" rel="noopener noreferrer" class="detail-title-link">
							{hoveredProject.title}
						</a>
					</h1>
				</div>

				<div class="detail-description">
					<p>{hoveredProject.description}</p>
				</div>
			{/if}
		</div>
	</div>
</div>

<style>
	.container {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
		width: 100%;
		max-width: 100%;
	}

	/* Featured Section */
	.featured-section {
		display: grid;
		grid-template-columns: 60% 40%;
		gap: 3rem;
		padding: 2rem 3rem;
		background: transparent;
		border-bottom: none;
		min-height: 420px;
		width: 100%;
		box-sizing: border-box;
	}

	.featured-image {
		width: 100%;
		height: 100%;
		border-radius: 12px;
		overflow: hidden;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
		transition: transform 0.3s ease;
		background: #F9F4ED;
	}

	.featured-image:hover {
		transform: scale(1.02);
	}

	.featured-image img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.featured-content {
		display: flex;
		flex-direction: column;
		justify-content: center;
		gap: 1rem;
		padding: 0.5rem 0;
	}

	.featured-badges {
		display: flex;
		gap: 0.75rem;
		align-items: center;
	}

	.latest-badge {
		display: inline-block;
		padding: 0.5rem 1rem;
		background: #F85C03;
		color: #ffffff;
		font-size: 0.875rem;
		font-family: 'Manrope', var(--font-heading);
		font-weight: 700;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		border-radius: 4px;
		box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
	}

	.featured-category {
		font-size: 0.875rem;
		font-family: 'Manrope', var(--font-heading);
		font-weight: 600;
		color: #6b7280;
		text-transform: uppercase;
		letter-spacing: 0.05em;
	}

	.featured-meta {
		display: flex;
		gap: 1rem;
		align-items: center;
	}

	.featured-publication {
		font-size: 0.95rem;
		font-family: 'Manrope', var(--font-heading);
		color: #6b7280;
		font-weight: 500;
	}

	.featured-date {
		font-size: 0.875rem;
		font-family: 'Manrope', var(--font-heading);
		color: #9ca3af;
	}

	.featured-title {
		font-size: 2.25rem;
		font-weight: 800;
		line-height: 1.2;
		margin: 0.5rem 0;
		letter-spacing: -0.02em;
		text-align: left;
	}

	.featured-title-link {
		color: #111827;
		text-decoration: none;
		transition: all 0.3s ease;
		border-bottom: 3px solid transparent;
	}

	.featured-title-link:hover {
		color: #111827;
		border-bottom: 3px solid #111827;
	}

	.featured-description {
		font-size: 1rem;
		line-height: 1.6;
		color: #374151;
		margin: 0.25rem 0 0 0;
	}

	/* Navigation Bar */
	.nav-bar {
		display: flex;
		gap: 2rem;
		padding: 1.5rem;
		border-bottom: none;
		background: #F9F4ED;
		position: sticky;
		top: 0;
		z-index: 100;
		flex-shrink: 0;
		border-radius: 12px 12px 0 0;
	}

	.nav-item {
		background: transparent;
		border: none;
		padding: 0.5rem 1rem;
		font-size: 0.9rem;
		font-family: var(--font-heading);
		color: #333;
		cursor: pointer;
		border-radius: 8px;
		transition: all 0.2s;
		font-weight: 500;
	}

	.nav-item:hover {
		background: #EDE8DC;
		color: #111827;
	}

	.nav-item.active {
		background: #E5DCC8;
		color: #111827;
		font-weight: 600;
	}

	/* Type Navigation Mobile */
	.type-nav-mobile {
		display: none;
	}

	/* Main Layout */
	.main-layout {
		display: grid;
		grid-template-columns: 45% 55%;
		flex: 1;
		overflow: hidden;
		position: relative;
		width: 100%;
		padding: 0 2rem;
		box-sizing: border-box;
		gap: 2rem;
	}

	/* Project List Container */
	.project-list-container {
		border-right: none;
		background: #F9F4ED;
		position: relative;
		height: 100%;
		display: flex;
		flex-direction: column;
		overflow-y: auto;
		overflow-x: hidden;
		border-radius: 12px;
		padding: 0;
		gap: 0;
	}

	/* Scrollable Sections Container */
	.sections-container {
		flex: 1;
		min-height: 0;
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
		padding: 0 1.5rem 1.5rem 1.5rem;
	}

	.project-section {
		position: relative;
		display: grid;
		grid-template-columns: 60px 1fr;
		background: #ffffff;
		border-radius: 12px;
		overflow: hidden;
		margin-bottom: 0;
	}

	.project-section:last-child {
		margin-bottom: 0;
	}

	/* Sticky Label */
	.sticky-label-wrapper {
		position: relative;
		height: 100%;
		background: #E5DCC8;
		border-radius: 12px 0 0 12px;
	}

	.sticky-label {
		position: sticky;
		top: 0;
		width: 60px;
		height: auto;
		display: flex;
		align-items: flex-start;
		justify-content: center;
		background: transparent;
		border: none;
		cursor: pointer;
		transition: opacity 0.2s ease;
		padding: 1rem 0;
		z-index: 90;
	}

	.sticky-label:hover {
		opacity: 0.7;
	}

	.sticky-label.active .label-text {
		font-weight: 700;
	}

	.label-text {
		writing-mode: vertical-rl;
		transform: rotate(180deg);
		font-size: 0.875rem;
		font-family: var(--font-heading);
		font-weight: 600;
		letter-spacing: 0.1em;
		text-transform: uppercase;
		color: #111827;
		pointer-events: none;
	}

	/* Project List */
	.project-list {
		background: #ffffff;
		padding: 0;
	}

	.project-item {
		width: 100%;
		padding: 1rem;
		border-bottom: 1px solid #f3f4f6;
		background: #ffffff;
		text-align: left;
		cursor: pointer;
		transition: all 0.2s ease;
		position: relative;
	}

	.project-item:hover {
		background: #f9fafb;
	}

	.project-item.hovered {
		background: #E5DCC8;
	}

	.project-item.hovered .project-title,
	.project-item.hovered .project-publication,
	.project-item.hovered .project-date,
	.project-item.hovered .project-separator {
		color: #111827;
	}


	.project-info {
		display: flex;
		flex-direction: column;
		gap: 0.25rem;
		line-height: 1.4;
		width: 100%;
	}

	.project-title {
		font-size: 1rem;
		font-family: var(--font-heading);
		font-weight: 500;
		color: #111827;
		transition: color 0.2s ease;
	}

	.project-publication {
		font-size: 0.75rem;
		font-family: var(--font-heading);
		color: #6b7280;
		transition: color 0.2s ease;
	}

	.project-date {
		font-size: 0.875rem;
		color: #9ca3af;
		transition: color 0.2s ease;
	}

	/* Project Detail */
	.project-detail {
		overflow-y: auto;
		padding: 3rem;
		background: #ffffff;
		transition: opacity 0.2s ease;
	}

	.detail-header {
		margin-bottom: 2rem;
	}

	.detail-meta {
		display: flex;
		gap: 1rem;
		margin-bottom: 0.75rem;
	}

	.detail-title {
		font-size: 2.5rem;
		font-weight: 700;
		margin: 0 0 0.5rem 0;
		line-height: 1.2;
		text-align: left;
	}

	.detail-title-link {
		color: #111827;
		text-decoration: none;
		transition: all 0.2s ease;
		display: inline-block;
		border-bottom: 2px solid transparent;
	}

	.detail-title-link:hover {
		color: #111827;
		border-bottom: 2px solid #111827;
	}

	.detail-category {
		font-size: 0.875rem;
		font-family: var(--font-heading);
		font-weight: 500;
		color: #111827;
		text-transform: uppercase;
		letter-spacing: 0.05em;
	}

	.detail-date {
		font-size: 0.875rem;
		font-family: var(--font-heading);
		color: #6b7280;
	}

	.detail-publication {
		font-size: 0.95rem;
		color: #6b7280;
		font-style: italic;
	}

	.detail-visualization {
		margin-bottom: 1.5rem;
		border-radius: 8px;
		overflow: hidden;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
		width: 100%;
		aspect-ratio: 3 / 2;
	}

	.detail-visualization img {
		width: 100%;
		height: 100%;
		display: block;
		object-fit: cover;
		background: #f8f9fa;
	}

	.detail-description {
		font-size: 1.125rem;
		line-height: 1.7;
		color: #374151;
	}

	.detail-description p {
		margin: 0;
	}

	/* Responsive Design */
	@media (max-width: 1024px) {
		.featured-section {
			grid-template-columns: 1fr;
			gap: 2rem;
			padding: 2rem 1.5rem;
			min-height: auto;
		}

		.featured-image {
			max-height: 300px;
		}

		.featured-title {
			font-size: 2rem;
		}

		.featured-description {
			font-size: 0.95rem;
		}

		.main-layout {
			grid-template-columns: 450px 1fr;
		}

		.project-detail {
			padding: 2rem;
		}

		.detail-title {
			font-size: 2rem;
		}
	}

	@media (max-width: 768px) {
		.container {
			padding: 0;
		}

		.featured-section {
			padding: 1rem;
			gap: 1rem;
			grid-template-columns: 1fr;
			min-height: auto;
		}

		.featured-image {
			max-height: 250px;
			border-radius: 8px;
		}

		.featured-title {
			font-size: 1.5rem;
			margin: 0.25rem 0;
		}

		.featured-description {
			font-size: 0.9rem;
			line-height: 1.5;
		}

		.featured-badges {
			gap: 0.5rem;
		}

		.latest-badge {
			padding: 0.4rem 0.8rem;
			font-size: 0.75rem;
		}

		.featured-category {
			font-size: 0.75rem;
		}

		.featured-publication {
			font-size: 0.85rem;
		}

		.featured-date {
			font-size: 0.75rem;
		}

		.nav-bar {
			gap: 0.75rem;
			padding: 0.75rem 1rem;
			overflow-x: auto;
			border-radius: 8px 8px 0 0;
		}

		.nav-item {
			padding: 0.4rem 0.8rem;
			font-size: 0.85rem;
			white-space: nowrap;
		}

		.type-nav-mobile {
			display: flex;
			gap: 0.5rem;
			padding: 0.75rem 1rem;
			background: #F9F4ED;
			border-top: 1px solid #E5DCC8;
		}

		.type-nav-item {
			flex: 1;
			background: transparent;
			border: none;
			padding: 0.5rem 1rem;
			font-size: 0.85rem;
			font-family: var(--font-heading);
			color: #333;
			cursor: pointer;
			border-radius: 6px;
			transition: all 0.2s;
			font-weight: 500;
		}

		.type-nav-item:hover {
			background: #EDE8DC;
			color: #111827;
		}

		.type-nav-item.active {
			background: #E5DCC8;
			color: #111827;
			font-weight: 600;
		}

		.main-layout {
			grid-template-columns: 1fr;
			grid-template-rows: auto 1fr;
			padding: 0 1rem;
			gap: 1rem;
		}

		.project-section {
			grid-template-columns: 1fr;
			border-radius: 8px;
		}

		.project-section.mobile-hidden {
			display: none;
		}

		.sticky-label-wrapper {
			display: none;
		}

		.project-list-container {
			border-right: none;
			border-bottom: 1px solid #e5e7eb;
			max-height: 45vh;
			border-radius: 8px;
		}

		.sections-container {
			padding: 0 1rem 1rem 1rem;
			gap: 1rem;
		}

		.project-item {
			padding: 0.75rem;
		}

		.project-title {
			font-size: 0.9rem;
		}

		.project-publication {
			font-size: 0.7rem;
		}

		.project-detail {
			padding: 1rem;
		}

		.detail-title {
			font-size: 1.5rem;
		}

		.detail-description {
			font-size: 1rem;
			line-height: 1.6;
		}

		.detail-category,
		.detail-date {
			font-size: 0.75rem;
		}

		.detail-visualization {
			border-radius: 8px;
			margin-bottom: 1rem;
		}
	}
</style>
