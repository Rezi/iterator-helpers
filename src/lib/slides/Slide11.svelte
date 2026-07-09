<div class="slide slide-11">
	<div class="bg-glow" aria-hidden="true"></div>
	<div class="bg-grid" aria-hidden="true"></div>

	<div class="content">
		<!-- Cherry illustration -->
		<div class="cherry-decoration" aria-hidden="true">
			<svg viewBox="0 0 180 100" width="180" height="100">
				<path
					d="M60,55 Q52,30 72,18"
					stroke="#2d6a27"
					stroke-width="3"
					fill="none"
					stroke-linecap="round"
				/>
				<path
					d="M90,48 Q95,22 85,10"
					stroke="#2d6a27"
					stroke-width="3"
					fill="none"
					stroke-linecap="round"
				/>
				<path d="M75,30 Q85,10 100,18 Q88,30 75,30" fill="#3a8030" />
				<circle cx="60" cy="68" r="18" fill="#CC1111" />
				<circle cx="55" cy="63" r="4.5" fill="rgba(255,255,255,0.2)" />
				<circle cx="90" cy="63" r="17" fill="#CC1111" />
				<circle cx="85" cy="58" r="4" fill="rgba(255,255,255,0.2)" />
				<path
					d="M118,52 Q128,25 118,12"
					stroke="#2d6a27"
					stroke-width="2.5"
					fill="none"
					stroke-linecap="round"
				/>
				<circle cx="118" cy="65" r="15" fill="#CC1111" />
				<circle cx="113" cy="61" r="3.5" fill="rgba(255,255,255,0.18)" />
				<text
					x="55"
					y="100"
					fill="#73c37c"
					font-size="14"
					font-family="Inter, sans-serif"
					font-weight="700"
					text-anchor="middle">✓</text
				>
				<text
					x="90"
					y="100"
					fill="#73c37c"
					font-size="14"
					font-family="Inter, sans-serif"
					font-weight="700"
					text-anchor="middle">✓</text
				>
				<text
					x="118"
					y="100"
					fill="#73c37c"
					font-size="14"
					font-family="Inter, sans-serif"
					font-weight="700"
					text-anchor="middle">✓</text
				>
			</svg>
		</div>

		<h1 class="thanks">Thank You!</h1>
		<p class="tagline">Just 3 good things to remember</p>

		<div class="takeaways">
			<div class="takeaway">
				<span class="takeaway-icon">💤</span>
				<span><strong>Lazy</strong> — runs only when consumed</span>
			</div>
			<div class="takeaway">
				<span class="takeaway-icon">🛑</span>
				<span><strong>Stops early</strong> — no wasted work</span>
			</div>
			<div class="takeaway">
				<span class="takeaway-icon">♾️</span>
				<span><strong>Infinite</strong> — works with endless sequences</span>
			</div>
		</div>

		<div class="divider"></div>

		<div class="presenter-block">
			<div class="presenter-name">Tomas Rezac</div>
			<div class="presenter-org">
				<span class="applifting-logo">⚡ Applifting</span>
				<span class="presenter-tagline">Lifting your ideas into digital orbit</span>
			</div>
		</div>
	</div>
</div>

<style>
	.slide-11 {
		background: radial-gradient(ellipse 70% 60% at 40% 50%, #1a1428 0%, #14141f 100%);
		justify-content: center;
		align-items: center;
	}

	.bg-glow {
		position: absolute;
		left: -120px;
		bottom: -120px;
		width: 500px;
		height: 500px;
		background: radial-gradient(circle, rgba(250, 198, 31, 0.06) 0%, transparent 70%);
		pointer-events: none;
	}

	.bg-grid {
		position: absolute;
		inset: 0;
		background-image:
			linear-gradient(rgba(250, 198, 31, 0.03) 1px, transparent 1px),
			linear-gradient(90deg, rgba(250, 198, 31, 0.03) 1px, transparent 1px);
		background-size: 52px 52px;
		pointer-events: none;
	}

	.content {
		position: relative;
		z-index: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 20px;
		text-align: center;
	}

	.cherry-decoration {
		filter: drop-shadow(0 6px 24px rgba(204, 17, 17, 0.3));
	}

	.thanks {
		font-size: clamp(3.5rem, 7vw, 5.5rem);
		font-weight: 900;
		color: var(--yellow);
		text-shadow: 0 0 60px rgba(250, 198, 31, 0.25);
		line-height: 1;
	}

	.tagline {
		font-size: var(--fsz-m);
		color: var(--gray);
		font-style: italic;
	}

	.takeaways {
		display: flex;
		gap: 24px;
	}

	.takeaway {
		display: flex;
		align-items: center;
		gap: 8px;
		background: rgba(255, 255, 255, 0.04);
		border: 1px solid rgba(255, 255, 255, 0.08);
		border-radius: 8px;
		padding: 10px 16px;
		font-size: var(--fsz-s);
		color: #c0c0d0;
	}

	.takeaway strong {
		color: var(--yellow);
	}

	.takeaway-icon {
		font-size: var(--fsz-m);
	}

	.divider {
		width: 280px;
		height: 1px;
		background: linear-gradient(90deg, transparent, rgba(250, 198, 31, 0.4), transparent);
	}

	.presenter-block {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 8px;
	}

	.presenter-name {
		font-size: var(--fsz-m);
		font-weight: 700;
		color: var(--light);
	}

	.presenter-org {
		display: flex;
		align-items: center;
		gap: 12px;
	}

	.applifting-logo {
		font-size: var(--fsz-s);
		font-weight: 800;
		letter-spacing: 0.08em;
		text-transform: uppercase;
		color: var(--yellow);
	}

	.presenter-tagline {
		font-size: var(--fsz-s);
		color: var(--gray);
		font-style: italic;
	}
</style>
