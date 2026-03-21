<script>
	const newsItems = [
		{
			date: '2024.08',
			publication: 'Forbes',
			description: 'Dedicated half the piece to citing my research, describing it as one of "the best and most insightful pieces of research" and "a superb analysis of the Olympic medals tables"',
			url: 'https://www.forbes.com/sites/stevendesmyter/2024/08/19/post-olympics-analysis-a-reader/'
		},
		{
			date: '2024.08',
			publication: 'Cosmopolitan',
			description: 'Referenced my tracking of Team USA\'s dominance of the Olympic medal table',
			url: 'https://www.cosmopolitan.com/entertainment/tv/a61852264/who-won-the-olympics/'
		}
	];

	</script>

<svelte:head>
	<title>About</title>
	<meta name="description" content="About Jinpeng Li" />
</svelte:head>

<div class="about-container">
	<!-- Photo and Intro Section -->
	<section class="intro-section">
		<div class="photo-container">
			<img src="/images/JP.jpg" alt="Jinpeng Li" class="photo" />
			<p class="photo-credit">Photo by <a href="https://krystalwon.work/index.html" target="_blank" rel="noopener noreferrer" class="photographer-link">Krystal Cheongeui Won</a></p>
		</div>
		<div class="intro-content">
			<p>
				In an era of information overload and blind conformity, I realized that narratives built on databases and documents have real staying power and impact.
			</p>
			<p>
				Since then, I've been building databases and using data analysis to uncover patterns and connections that support traditional storytelling. I also translate complex realities into something comprehensible and accessible through data visualizations, maps, and tables—sometimes, these become the story itself.
			</p>
			
			<div class="career-section">
				<h3>Currently</h3>
				<p>
					I'm a Senior Data Visualization Editor at <a href="https://www.emarketer.com/" target="_blank" rel="noopener noreferrer">EMARKETER</a> in New York.
				</p>
			</div>

			<div class="career-section">
				<h3>Previously</h3>
				<p>
					I worked in different types of newsrooms, collaborated with reporters across beats, and covered a variety of stories on local, national and foreign assignments. I was a data graphics fellow at <a href="https://www.businessinsider.com/author/jinpeng-li" target="_blank" rel="noopener noreferrer">Business Insider</a>, a data reporting fellow at <a href="https://www.washingtonpost.com/people/jinpeng-li/" target="_blank" rel="noopener noreferrer">The Washington Post</a> and <a href="https://investigativereportingworkshop.org/" target="_blank" rel="noopener noreferrer">Investigative Reporting Workshop</a>, and an election researcher at The Dallas Morning News.
				</p>
				<p>
					I hold a master's degree in journalism and media from UT Austin. I also trained at Investigative Reporters & Editors at the University of Missouri, supported by the Dow Jones News Fund. 
				</p>
			</div>

			<div class="career-section">
				<h3>One More Thing</h3>
				<p>
					Data can be biased, hypotheses can be wrong, methodologies can be limited, and graphics can be misleading. Every improvement in my work depends on feedback from editors and colleagues. I'm always eager to hear people's thoughts. I'm committed to creating a safe and welcoming space to discuss works, so please reach out!
				</p>
			</div>
		</div>
	</section>

	<!-- In the News Section -->
	<section class="impact-section">
		<h2>In the News</h2>
		<table class="news-table">
			<thead>
				<tr>
					<th class="col-date">Time</th>
					<th class="col-publication">Publication</th>
					<th class="col-description">How they used my work</th>
				</tr>
			</thead>
			<tbody>
				{#each newsItems as item}
					<tr class="news-row" on:click={() => window.open(item.url, '_blank', 'noopener,noreferrer')} role="link" tabindex="0" on:keydown={(e) => e.key === 'Enter' && window.open(item.url, '_blank', 'noopener,noreferrer')}>
						<td class="col-date">{item.date}</td>
						<td class="col-publication">{item.publication}</td>
						<td class="col-description">{item.description}</td>
					</tr>
				{/each}
			</tbody>
		</table>
	</section>

	<!-- Awards Section -->
	<section class="awards-section">
		<h2>Awards</h2>
		<p class="award-item">Part of a team at Business Insider that won the <a href="https://www.businessinsider.com/business-insider-wins-first-george-polk-award-2026-2" target="_blank" rel="noopener noreferrer"><strong>George Polk Awards</strong></a> in Environmental Reporting for coverage of <em>The True Cost of Data Centers</em>, 2026.</p>
	</section>
</div>

<style>
	.about-container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 2rem;
	}

	/* Intro Section */
	.intro-section {
		display: grid;
		grid-template-columns: 300px 1fr;
		gap: 3rem;
		margin-bottom: 2rem;
		align-items: start;
	}

	.photo-container {
		position: sticky;
		top: 2rem;
	}

	.photo {
		width: 300px;
		height: 400px;
		object-fit: cover;
		border-radius: 12px;
	}

	.photo-credit {
		margin-top: 0.5rem;
		font-size: 0.75rem;
		color: #6b7280;
		text-align: center;
	}

	.photographer-link {
		color: #6b7280;
		font-style: italic;
		text-decoration: none;
	}

	.photographer-link:hover {
		color: #374151;
		text-decoration: underline;
	}

	.intro-content h1 {
		font-size: 2.5rem;
		font-weight: 700;
		margin-bottom: 1.5rem;
		color: #111827;
	}

	.intro-content p {
		font-size: 1.1rem;
		line-height: 1.8;
		color: #374151;
		margin-bottom: 1.5rem;
	}

	/* Career Sections */
	.career-section {
		margin-top: 2.5rem;
		padding-left: 1.25rem;
		border-left: 3px solid #ea580c;
	}

	.career-section h3 {
		font-size: 1.3rem;
		font-weight: 700;
		color: #111827;
		margin-bottom: 0.75rem;
		letter-spacing: -0.01em;
	}

	.career-section p {
		margin-bottom: 1rem;
	}

	.career-section p:last-child {
		margin-bottom: 0;
	}

	/* Contact Section */
	.contact-section {
		background: #F9F4ED;
		border-radius: 12px;
		padding: 2.5rem;
		margin-bottom: 3rem;
	}

	.contact-section h2 {
		font-size: 2rem;
		font-weight: 700;
		margin-bottom: 1.5rem;
		color: #111827;
	}

	.contact-content p {
		font-size: 1.1rem;
		color: #374151;
		margin-bottom: 1.5rem;
	}

	.contact-details {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	.contact-item {
		font-size: 1rem;
		color: #374151;
	}

	.contact-item strong {
		color: #111827;
		margin-right: 0.5rem;
		font-family: var(--font-heading);
		font-weight: 600;
	}

	/* Impact Section */
	.impact-section {
		background: transparent;
		padding: 1rem 0 0 0;
		margin-top: 0.5rem;
	}

	.impact-section h2 {
		font-size: 2rem;
		font-weight: 700;
		color: #111827;
		letter-spacing: -0.01em;
		margin-bottom: 1rem;
	}

	.news-table {
		width: 100%;
		border-collapse: collapse;
		font-size: 1rem;
	}

	.news-table thead tr th {
		padding: 0 1.5rem 0.875rem 0;
		text-align: left;
		font-size: 0.75rem;
		font-family: var(--font-heading);
		font-weight: 600;
		color: #d1d5db;
		border-bottom: 1px solid #e5e7eb;
	}

	.news-row {
		cursor: pointer;
		transition: all 0.2s ease;
		border-bottom: 1px solid #f3f4f6;
	}

	.news-row:hover {
		background: transparent;
	}

	.news-row:hover .col-publication {
		color: #F85C03;
	}

	.news-row:hover .col-date {
		color: #F85C03;
	}

	.news-row:hover .col-description {
		color: #111827;
	}

	.news-row td {
		padding: 1rem 1rem 1rem 0;
		line-height: 1.7;
		vertical-align: top;
	}

	.col-date {
		white-space: nowrap;
		width: 110px;
		color: #9ca3af;
		font-size: 0.95rem;
		font-family: var(--font-heading);
		font-weight: 500;
		transition: color 0.2s ease;
	}

	.col-publication {
		width: 180px;
		font-weight: 400;
		color: #6b7280;
		font-size: 1.05rem;
		transition: color 0.2s ease;
	}

	.col-description {
		color: #6b7280;
		font-size: 1rem;
		transition: color 0.2s ease;
	}

	/* Awards Section */
	.awards-section {
		padding: 1rem 0 0 0;
		margin-top: 0.5rem;
	}

	.awards-section h2 {
		font-size: 2rem;
		font-weight: 700;
		color: #111827;
		letter-spacing: -0.01em;
		margin-bottom: 0.75rem;
	}

	.award-item {
		font-size: 1rem;
		line-height: 1.7;
		color: #6b7280;
		margin: 0;
	}

	.award-item a {
		color: inherit;
		text-decoration: none;
		transition: color 0.2s ease;
	}

	.award-item a:hover {
		color: #F85C03;
	}

	/* Responsive */
	@media (max-width: 768px) {
		.about-container {
			padding: 1rem;
		}

		.impact-section h2,
		.awards-section h2 {
			font-size: 1.5rem;
			margin-bottom: 0.5rem;
		}

		.impact-section,
		.awards-section {
			padding: 0;
			margin-top: 1rem;
		}

		.award-item {
			font-size: 0.95rem;
			line-height: 1.6;
		}

		.news-table thead {
			display: none;
		}

		.news-table,
		.news-table tbody,
		.news-row,
		.news-row td {
			display: block;
			width: 100%;
		}

		.news-row {
			padding: 1rem 0;
			border-bottom: 1px solid #f3f4f6;
		}

		.news-row td {
			padding: 0;
			border: none;
		}

		.col-date {
			font-size: 0.8rem;
			margin-bottom: 0.2rem;
		}

		.col-publication {
			font-size: 1rem;
			margin-bottom: 0.4rem;
		}

		.col-description {
			font-size: 0.9rem;
		}

		.intro-section {
			grid-template-columns: 1fr;
			gap: 1.5rem;
			margin-bottom: 1rem;
		}


		.photo {
			width: 100%;
			max-width: 280px;
			height: 350px;
			margin: 0 auto;
			display: block;
		}

		.photo-container {
			position: static;
			text-align: center;
		}

		.intro-content p {
			font-size: 1rem;
			line-height: 1.7;
			margin-bottom: 1.25rem;
		}

		.contact-section {
			padding: 1.5rem;
			margin-bottom: 1.5rem;
		}

		.contact-section h2 {
			font-size: 1.5rem;
			margin-bottom: 1rem;
		}

		.contact-content p,
		.news-item p {
			font-size: 1rem;
			line-height: 1.6;
		}
	}
</style>
