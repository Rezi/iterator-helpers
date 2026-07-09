<div class="slide slide-1">
	<!-- Background decoration -->
	<div class="bg-grid" aria-hidden="true"></div>
	<div class="bg-glow" aria-hidden="true"></div>

	<!-- Top bar -->
	<div class="top-bar">
		<span class="applifting-logo">⚡ Applifting</span>
	</div>

	<!-- Center content -->
	<div class="hero">
		<div class="tag-badge">ECMAScript 2025</div>
		<h1 class="title">
			<span class="line-1">Iterator</span>
			<span class="line-2 accent">Helpers</span>
		</h1>
		<p class="subtitle">Lazy evaluation for modern JavaScript</p>
	</div>

	<!-- Bottom presenter -->
	<div class="presenter-bar">
		<div class="divider-line"></div>
		<div class="presenter-info">
			<span class="presenter-name">Tomas Rezac</span>
			<span class="dot">·</span>
			<span class="presenter-org">Applifting</span>
		</div>
	</div>
</div>

<style>
	.slide-1 {
		justify-content: space-between;
		background: radial-gradient(ellipse 70% 60% at 60% 40%, #1e1a2e 0%, #14141f 100%);
	}

	.bg-grid {
		position: absolute;
		inset: 0;
		background-image:
			linear-gradient(rgba(250, 198, 31, 0.04) 1px, transparent 1px),
			linear-gradient(90deg, rgba(250, 198, 31, 0.04) 1px, transparent 1px);
		background-size: 48px 48px;
		pointer-events: none;
	}

	.bg-glow {
		position: absolute;
		right: -100px;
		top: -100px;
		width: 600px;
		height: 600px;
		background: radial-gradient(circle, rgba(250, 198, 31, 0.06) 0%, transparent 70%);
		pointer-events: none;
	}

	.top-bar {
		position: relative;
		z-index: 1;
	}

	.hero {
		position: relative;
		z-index: 1;
		flex: 1;
		display: flex;
		flex-direction: column;
		justify-content: center;
		gap: 24px;
	}

	.title {
		display: flex;
		flex-direction: column;
		font-size: clamp(4rem, 9vw, 7rem);
		font-weight: 900;
		line-height: 1;
		letter-spacing: -0.02em;
	}

	.line-1 {
		color: #f0f0f0;
	}

	.line-2 {
		color: #fac61f;
		text-shadow: 0 0 60px rgba(250, 198, 31, 0.3);
	}

	.subtitle {
		font-size: 2rem;
		color: #848484;
		font-weight: 400;
		letter-spacing: 0.02em;
	}

	.presenter-bar {
		position: relative;
		z-index: 1;
	}

	.divider-line {
		width: 100%;
		height: 1px;
		background: linear-gradient(90deg, rgba(250, 198, 31, 0.5) 0%, transparent 60%);
		margin-bottom: 20px;
	}

	.presenter-info {
		display: flex;
		align-items: center;
		gap: 12px;
		font-size: var(--fsz-lg);
		color: #848484;
	}

	.presenter-name {
		color: #f0f0f0;
		font-weight: 600;
	}

	.dot {
		color: #fac61f;
	}

	.presenter-org {
		font-weight: 500;
	}
</style>
