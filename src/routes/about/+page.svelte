<svelte:head>
	<title>About</title>
	<meta name="description" content="About Jinpeng Li" />
</svelte:head>

<div class="about-container">
	<!-- Photo and Intro Section -->
	<section class="intro-section">
		<div class="photo-container">
			<img src="/images/JP.jpg" alt="Jinpeng Li" class="photo" />
			<p class="photo-credit">Photo by Krystal Cheongeui Won</p>
		</div>
		<div class="intro-content">
			<p>
				When I arrived in the States in 2022, data journalism felt like the last glimmer of hope that traditional journalism was showing me. In an era of information overload and blind conformity, I realized that narratives built on databases and documents have real staying power and impact.
			</p>
			<p>
				Since then, I've been building databases and using data analysis to uncover patterns and connections that support traditional reporting. I also translate complex realities into something comprehensible and accessible through data visualizations, maps, and tables—sometimes, these become the story itself.
			</p>
			<p>
				I've worked in different types of newsrooms and collaborated with reporters across beats. Previously, I was a data graphics fellow at <a href="https://www.businessinsider.com/author/jinpeng-li" target="_blank" rel="noopener noreferrer">Business Insider</a>, a data reporting fellow at <a href="https://www.washingtonpost.com/people/jinpeng-li/" target="_blank" rel="noopener noreferrer">The Washington Post</a> and Investigative Reporting Workshop, and an election researcher at The Dallas Morning News.
			</p>
			<p>
				I hold a master's degree in journalism and media from UT-Austin, where I was awarded the Dallas Morning News Fellowship for Journalism Innovation, the Norris G. Davis Fellowship, and a TPEG scholarship. I also trained at Investigative Reporters & Editors at the University of Missouri, supported by the Dow Jones News Fund. Before moving to the US, I worked as a business reporter in China.
			</p>
			<p>
				Data can be biased, hypotheses can be wrong, methodologies can be limited, and graphics can be inaccessible. Every improvement in my work depends on feedback from editors and colleagues. I'm always eager to hear your thoughts. I'm committed to creating a safe and welcoming space to discuss works, so please reach out!
			</p>
		</div>
	</section>

	<!-- Contact Section -->
	<section class="contact-section">
		<div class="contact-content">
			<div class="contact-details">
				<div class="contact-item">
					<strong>Email:</strong> forjpli at gmail dot com
				</div>
				<div class="contact-item">
					<strong>Signal:</strong> itsjpli.14
				</div>
				<div class="contact-item">
					<strong>📍:</strong> Jersey City, NJ
				</div>
			</div>
		</div>
	</section>

	<!-- In the News Section -->
	<section class="impact-section">
		<h2>In the News</h2>
		<div class="impact-content">
			<div class="news-item">
				<h3><a href="https://www.forbes.com/sites/stevendesmyter/2024/08/19/post-olympics-analysis-a-reader/" target="_blank" rel="noopener noreferrer">Forbes, Aug. 2024</a></h3>
				<p>
					Forbes dedicated half the piece to citing my research, describing it as one of "the best and most insightful pieces of research" and "a superb analysis of the Olympic medals tables"
				</p>
			</div>
			<div class="news-item">
				<h3><a href="https://www.cosmopolitan.com/entertainment/tv/a61852264/who-won-the-olympics/" target="_blank" rel="noopener noreferrer">Cosmopolitan, Aug. 2024</a></h3>
				<p>
					Cosmopolitan references my tracking of Team USA's dominance of the Olympic medal table.
				</p>
			</div>
		</div>
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
		margin-bottom: 4rem;
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
	}

	/* Impact Section */
	.impact-section {
		background: #F9F4ED;
		border-radius: 12px;
		padding: 2.5rem;
	}

	.impact-section h2 {
		font-size: 2rem;
		font-weight: 700;
		margin-bottom: 1.5rem;
		color: #111827;
	}

	.impact-content {
		display: flex;
		flex-direction: column;
		gap: 2rem;
	}

	.news-item h3 {
		font-size: 1.3rem;
		font-weight: 600;
		margin-bottom: 0.75rem;
	}

	.news-item h3 a {
		color: #111827;
		text-decoration: none;
	}

	.news-item h3 a:hover {
		color: #6b7280;
		text-decoration: underline;
	}

	.news-item p {
		font-size: 1.1rem;
		color: #374151;
		line-height: 1.8;
	}

	/* Responsive */
	@media (max-width: 768px) {
		.about-container {
			padding: 1rem;
		}

		.intro-section {
			grid-template-columns: 1fr;
			gap: 2rem;
			margin-bottom: 2rem;
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

		.contact-section,
		.impact-section {
			padding: 1.5rem;
			margin-bottom: 1.5rem;
		}

		.contact-section h2,
		.impact-section h2 {
			font-size: 1.5rem;
			margin-bottom: 1rem;
		}

		.contact-content p,
		.news-item p {
			font-size: 1rem;
			line-height: 1.6;
		}

		.news-item h3 {
			font-size: 1.1rem;
		}
	}
</style>
