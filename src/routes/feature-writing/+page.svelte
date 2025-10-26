<script>
	import recentWork from '$lib/data/feature-writing.json';
</script>

<svelte:head>
	<title>Feature Writing - JP Li</title>
</svelte:head>

<div class="container">
	<p class="notice">
		I code, but sometimes I'm on the road.<br />
		This page is for Chinese-speaking audiences and media.
	</p>

	<div class="intro-section">
		<div class="bio-block">
			<p class="intro-text chinese">
				李金朋是驻纽约的自由记者,长期从事分析报道和特稿写作。他的作品见于端传媒、财新网、《第一财经杂志》等主流媒体,读者覆盖数百万。
			</p>
			<p class="intro-text english">
				Jinpeng Li is a New York City-based freelance journalist specializing in analytical and feature writing. His work has reached millions of readers across the Chinese-speaking world through top-tier publications including Initium Media, Caixin Media, and Yimagazine.
			</p>
		</div>

		<div class="bio-block">
			<p class="intro-text chinese">
				为了让代表性不足的亚裔群体发声，纠正中文世界对美国社会长期以来基于错误信息的误解，他致力于创作不受党派偏见影响、以人为本的报道。他主要报道美国政治、政策与国际事务。
			</p>
			<p class="intro-text english">
				He recognizes living in the US as a privilege. To amplify underrepresented Asian community voices and counter the misinformation that shapes Chinese-speaking audiences' understanding of American society, he writes human-drive narratives free from partisan bias. His work covers US politics, policy, and international affairs.
			</p>
		</div>

		<div class="bio-block">
			<p class="intro-text chinese">
				他支持新闻自由，与多家独立媒体合作，目前是端传媒的固定撰稿人。他的特稿写作方法要求每篇报道至少采访三类立场不同的利益相关者——他的单篇报道平均采访八位消息来源。
			</p>
			<p class="intro-text english">
				In support of press freedom, he collaborates with independent media outlets and is currently a regular contributor to Initium Media. His feature writing methodology requires interviewing at least three types of stakeholders with differing perspectives for each story—he has averaged eight sources per piece.
			</p>
		</div>

		<div class="bio-block contact">
			<p class="intro-text chinese">
				工作邀约请联系: 高先生,微信:chicest14
			</p>
			<p class="intro-text english">
				For collaboration inquiries, please contact: Mr. Gao, WeChat: chicest14
			</p>
		</div>
	</div>

	<div class="recent-work-section">
		<h2>Recent Work</h2>
		<div class="work-list">
			{#each recentWork as work}
				<a href={work.url} class="work-item" target="_blank" rel="noopener noreferrer">
					<div class="work-image">
						<img src={work.image} alt={work.titleEnglish} />
					</div>
					<div class="work-content">
						<div class="work-titles">
							<h3 class="work-title-chinese">{work.titleChinese}</h3>
							<h4 class="work-title-english">{work.titleEnglish}</h4>
						</div>
						<div class="work-meta">
							<span class="work-publication">{work.publication}</span>
							<span class="work-date">{work.date}</span>
						</div>
						{#if work.description}
							<p class="work-description">{work.description}</p>
						{/if}
					</div>
				</a>
			{/each}
		</div>
	</div>
</div>

<style>
	.container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 2rem 0;
	}

	.notice {
		font-size: 0.75rem;
		color: #9ca3af;
		font-family: 'Lora', serif;
		line-height: 1.5;
		margin: 0 0 2rem 0;
		text-align: center;
	}

	.intro-section {
		margin-bottom: 4rem;
	}

	.bio-block {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 2rem;
		margin-bottom: 1.5rem;
		padding-bottom: 1.5rem;
		border-bottom: 1px solid #e5e7eb;
	}

	.bio-block:last-child {
		border-bottom: none;
	}

	.bio-block.contact {
		margin-top: 1rem;
		padding-top: 0;
		border-top: none;
		border-bottom: none;
	}

	.intro-text {
		font-size: 1rem;
		font-family: var(--font-heading);
		color: #333;
		line-height: 1.8;
		margin: 0;
	}

	.intro-text.chinese {
		font-size: 1.05rem;
		color: #1a1a1a;
		font-family: 'SimSun', '宋体', serif;
	}

	.intro-text.english {
		font-size: 0.95rem;
		color: #6b7280;
		font-family: 'Lora', serif;
	}

	.recent-work-section {
		margin-top: 3rem;
	}

	h2 {
		font-size: 2rem;
		font-family: 'Manrope', var(--font-heading);
		color: #1a1a1a;
		margin-bottom: 2rem;
	}

	.work-list {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	.work-item {
		display: flex;
		gap: 1rem;
		text-decoration: none;
		transition: transform 0.2s ease;
		border-bottom: 1px solid #e5e7eb;
		padding-bottom: 1rem;
	}

	.work-item:last-child {
		border-bottom: none;
	}

	.work-item:hover {
		transform: translateX(8px);
	}

	.work-image {
		flex-shrink: 0;
		width: 30%;
		aspect-ratio: 16 / 9;
		max-height: 140px;
		overflow: hidden;
		border-radius: 4px;
		background: #f3f4f6;
	}

	.work-image img {
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.work-content {
		flex: 1;
		display: flex;
		flex-direction: column;
		gap: 0.5rem;
	}

	.work-titles {
		display: flex;
		align-items: baseline;
		gap: 0.75rem;
		flex-wrap: wrap;
	}

	.work-title-chinese {
		font-size: 1.15rem;
		font-family: 'SimSun', '宋体', serif;
		color: #1a1a1a;
		margin: 0;
		line-height: 1.3;
	}

	.work-title-english {
		font-size: 0.9rem;
		font-family: 'Lora', serif;
		color: #4b5563;
		font-weight: 400;
		margin: 0;
		line-height: 1.3;
	}

	.work-meta {
		display: flex;
		gap: 1rem;
		align-items: center;
	}

	.work-publication {
		font-size: 0.85rem;
		font-family: 'Lora', serif;
		color: #9ca3af;
		font-weight: 400;
	}

	.work-date {
		font-size: 0.85rem;
		font-family: 'Lora', serif;
		color: #9ca3af;
	}

	.work-description {
		font-size: 0.85rem;
		font-family: 'Lora', serif;
		color: #6b7280;
		line-height: 1.5;
		margin: 0.25rem 0 0 0;
	}
</style>
