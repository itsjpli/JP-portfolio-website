<script>
	// Feature Writing page content will go here
	const recentWork = [
		// Placeholder data - you can replace with actual articles
		{
			title: "德州土地法案反抗者 Texas Asian Land Bill",
			publication: "Initium Media",
			date: "Jan 2025",
			url: "https://theinitium.com/zh-hans/article/20250114-international-chinese-american-commuinity-protest-against-texas-property-bill"
		},
		{
			title: "TikTok关门 TikTok shut down",
			publication: "Yimagazine",
			date: "Jan 2025",
			url: "https://mp.weixin.qq.com/s/vAGNAA7ycekYKlo9zecD_A"
		},
		{
			title: "TikTok电商 TikTok Chinese Seller",
			publication: "Yimagazine",
			date: "Dec 2024",
			url: "https://mp.weixin.qq.com/s/b6Lp2g2xzWyj2u7k7KBASQ"
		}
	];
</script>

<svelte:head>
	<title>Feature Writing - JP Li</title>
</svelte:head>

<div class="container">
	<div class="intro-section">
		<div class="bio-block">
			<p class="intro-text chinese">
				李金朋是驻纽约的自由记者,长期从事分析报道和特稿写作。他的作品常见于端传媒、财新网、《第一财经杂志》等主流媒体,读者覆盖数百万。
			</p>
			<p class="intro-text english">
				Jinpeng Li is a New York City-based freelance journalist specializing in analytical and feature writing. His work has reached millions of readers across the Chinese-speaking world through top-tier publications including Initium Media, Caixin Media, and Yimagazine.
			</p>
		</div>

		<div class="bio-block">
			<p class="intro-text chinese">
				他目前为端传媒撰稿,报道美国政治、社会及国际事务,同时也为硅谷101撰稿,关注科技行业的资本与权力。
			</p>
			<p class="intro-text english">
				As a regular contributor to Initium Media, he covers US politics, society, and international affairs. He also reports on money and power in the tech industry for TheValley101.
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
				<div class="work-item">
					<a href={work.url} class="work-title" target="_blank" rel="noopener noreferrer">
						{work.title}
					</a>
					<span class="work-date">{work.date}</span>
				</div>
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

	.intro-section {
		margin-bottom: 4rem;
	}

	.bio-block {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 3rem;
		margin-bottom: 2.5rem;
		padding-bottom: 2.5rem;
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
		font-size: 1.1rem;
		font-family: var(--font-heading);
		color: #333;
		line-height: 1.8;
		margin: 0;
	}

	.intro-text.chinese {
		font-size: 1.15rem;
		color: #1a1a1a;
		font-family: 'SimSun', '宋体', serif;
	}

	.intro-text.english {
		font-size: 1.05rem;
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
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 2rem 3rem;
	}

	.work-item {
		display: flex;
		justify-content: space-between;
		align-items: baseline;
		gap: 1rem;
	}

	.work-title {
		font-size: 1.1rem;
		font-family: 'Lora', serif;
		color: #1a1a1a;
		text-decoration: none;
		transition: color 0.2s ease;
		flex: 1;
	}

	.work-title:hover {
		color: #F85C03;
	}

	.work-date {
		font-size: 0.95rem;
		font-family: 'Lora', serif;
		color: #6b7280;
		white-space: nowrap;
	}
</style>
