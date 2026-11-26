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
				Jinpeng "JP" Li is a creator journalist based in New York. He covers AI and the forces around it, from the technology itself to the money and politics that shape it. He reports for news outlets and runs his own video channel, and he treats both as parts of the same practice.
			</p>
			<p>
				More and more people now get their news from short video. Li believes journalism has to follow that attention, and he sees each new medium as a chance to test a new way of reporting. Like a growing number of reporters who have built their own newsletters, podcasts and video channels, he treats the relationship with his audience as part of the work itself.
			</p>
			<p>
				That belief led him to start <a href="https://xhslink.cn/m/2mIsSqUtxNN" target="_blank" rel="noopener noreferrer">CRACK (凿壁而入)</a>, a Chinese-language video channel on Silicon Valley and Wall Street. Its name evokes chiseling through a wall, and the channel tries to do the same to the news. Each video starts from a story people are already talking about, then digs into the details and nuance the headlines leave out, building the explanation around his own observations.
			</p>

			<div class="career-section">
				<h3>Currently</h3>
				<ul class="career-list">
					<li>Contributing Writer at <a href="https://theinitium.com/author/jinpengli-zh-hans/" target="_blank" rel="noopener noreferrer">Initium Media</a>, writing long-form reporting on technology, politics and the people they affect</li>
					<li>Founder of <a href="https://xhslink.cn/m/2mIsSqUtxNN" target="_blank" rel="noopener noreferrer">CRACK (凿壁而入)</a>, a social-first explainer video channel</li>
					<li>Content consultant for independent media outlets, including 81st Media and The Valley 101</li>
				</ul>
			</div>

			<div class="career-section">
				<h3>Previously</h3>
				<p>
					Li has worked across newsrooms and beats, on local, national and foreign assignments. As a data journalist, he was a data graphics fellow at <a href="https://www.businessinsider.com/author/jinpeng-li" target="_blank" rel="noopener noreferrer">Business Insider</a> and a data reporting fellow at <a href="https://www.washingtonpost.com/people/jinpeng-li/" target="_blank" rel="noopener noreferrer">The Washington Post</a> and the <a href="https://investigativereportingworkshop.org/" target="_blank" rel="noopener noreferrer">Investigative Reporting Workshop</a>. He began his career as a business reporter at Caixin Media and Yicai in Shanghai.
				</p>
				<p>
					Li came to data journalism in search of narratives that last and hold up, the kind built on databases and documents. AI has since accelerated that craft, putting data-driven storytelling within reach of more newsrooms than ever. Yet even work with real staying power can go unheard. What he looks for now is a narrative people choose to trust, one carried by a voice they know and a relationship they can return to.
				</p>
				<p>
					Li holds a master's degree in journalism and media from the University of Texas at Austin. He also trained at Investigative Reporters & Editors, with support from the Dow Jones News Fund. He has served as a judge for several major journalism competitions.
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
		<p class="award-intro">Part of a team at Business Insider for coverage of <em>The True Cost of Data Centers</em>, 2026:</p>
		<ul class="award-list">
			<li><a href="https://www.businessinsider.com/business-insider-wins-first-george-polk-award-2026-2" target="_blank" rel="noopener noreferrer"><strong>George Polk Awards</strong></a> in Environmental Reporting (Winner)</li>
			<li><strong>Gerald Loeb Awards</strong> in Investigative (Finalist)</li>
			<li><strong>Online Journalism Awards</strong> in The University of Florida Award in Investigative Data Journalism (Finalist)</li>
			<li><strong>SABEW Awards</strong> in Data Journalism (Honorable Mention)</li>
			<li><strong>Deadline Club Awards</strong> in Business Investigative Reporting (Finalist)</li>
		</ul>
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

	.intro-content {
		max-width: 580px;
	}

	.intro-content p {
		font-size: 1rem;
		line-height: 1.75;
		color: #374151;
		margin-bottom: 1.25rem;
		text-align: justify;
		hyphens: none;
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

	.career-list {
		list-style: none;
		padding: 0;
		margin: 0;
	}

	.career-list li {
		font-size: 1rem;
		line-height: 1.75;
		color: #374151;
		margin-bottom: 0.75rem;
		padding-left: 1.5rem;
		position: relative;
	}

	.career-list li::before {
		content: "•";
		position: absolute;
		left: 0;
		color: #ea580c;
		font-weight: bold;
		font-size: 1.2rem;
	}

	.career-list li:last-child {
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
		max-width: calc(300px + 3rem + 580px);
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
		max-width: calc(300px + 3rem + 580px);
	}

	.awards-section h2 {
		font-size: 2rem;
		font-weight: 700;
		color: #111827;
		letter-spacing: -0.01em;
		margin-bottom: 0.75rem;
	}

	.award-intro {
		font-size: 1rem;
		line-height: 1.7;
		color: #6b7280;
		margin-bottom: 0.75rem;
	}

	.award-list {
		list-style: none;
		padding: 0;
		margin: 0;
	}

	.award-list li {
		font-size: 1rem;
		line-height: 1.7;
		color: #6b7280;
		margin-bottom: 0.5rem;
		padding-left: 1.25rem;
		position: relative;
	}

	.award-list li::before {
		content: "•";
		position: absolute;
		left: 0;
		color: #ea580c;
		font-weight: bold;
	}

	.award-list li a {
		color: inherit;
		text-decoration: none;
		transition: color 0.2s ease;
	}

	.award-list li a:hover {
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

		.award-intro {
			font-size: 0.95rem;
			line-height: 1.6;
		}

		.award-list li {
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
