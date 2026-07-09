<div class="slide slide-4">
	<div class="slide-heading">The <span class="accent">Cherry Basket</span> Problem</div>
	<div class="heading-bar"></div>

	<div class="body">
		<!-- Left: story text -->
		<div class="story">
			<p class="story-lead">
				You have a basket with <strong>100 cherries</strong>.
			</p>

			<div class="stats-row">
				<div class="stat good">
					<span class="stat-num">50</span>
					<span class="stat-label">Good cherries 🍒</span>
				</div>
				<div class="stat bad">
					<span class="stat-num">50</span>
					<span class="stat-label">Wormy cherries 🐛</span>
				</div>
			</div>

			<div class="goal-box">
				<span class="goal-icon">🎯</span>
				<div>
					<div class="goal-title">The Goal</div>
					<div class="goal-text">Pick just <strong>3 good cherries</strong></div>
				</div>
			</div>

			<p class="question">How do you approach this?</p>
		</div>

		<!-- Right: illustration -->
		<div class="illustration">
			<svg viewBox="0 0 340 310" xmlns="http://www.w3.org/2000/svg" class="basket-svg">
				<!-- Basket handle -->
				<path
					d="M100,130 Q170,45 240,130"
					stroke="#9B7040"
					stroke-width="11"
					fill="none"
					stroke-linecap="round"
				/>

				<!-- Basket body -->
				<path d="M65,140 Q62,255 170,255 Q278,255 275,140 Z" fill="#A07040" />

				<!-- Basket weave horizontal lines -->
				<path d="M70,160 Q170,170 270,160" stroke="#7A5030" stroke-width="3.5" fill="none" />
				<path d="M67,182 Q170,193 273,182" stroke="#7A5030" stroke-width="3.5" fill="none" />
				<path d="M65,204 Q170,216 275,204" stroke="#7A5030" stroke-width="3.5" fill="none" />
				<path d="M66,226 Q170,238 274,226" stroke="#7A5030" stroke-width="3" fill="none" />
				<path d="M68,247 Q170,256 272,247" stroke="#7A5030" stroke-width="2" fill="none" />

				<!-- Basket vertical weave -->
				<path d="M98,140 Q93,195 88,255" stroke="#7A5030" stroke-width="2" fill="none" />
				<path d="M130,140 Q128,195 126,255" stroke="#7A5030" stroke-width="2" fill="none" />
				<path d="M162,140 L162,255" stroke="#7A5030" stroke-width="2" />
				<path d="M200,140 Q202,195 204,255" stroke="#7A5030" stroke-width="2" fill="none" />
				<path d="M235,140 Q238,195 241,255" stroke="#7A5030" stroke-width="2" fill="none" />

				<!-- Basket rim -->
				<ellipse cx="170" cy="137" rx="106" ry="22" fill="#C09050" />

				<!-- Cherry 1 — GOOD -->
				<path
					d="M110,112 Q104,88 118,74"
					stroke="#2d6a27"
					stroke-width="2.5"
					fill="none"
					stroke-linecap="round"
				/>
				<circle cx="110" cy="120" r="15" fill="#CC1111" />
				<circle cx="106" cy="116" r="4" fill="rgba(255,255,255,0.18)" />

				<!-- Cherry 2 — GOOD -->
				<path
					d="M148,105 Q155,80 145,66"
					stroke="#2d6a27"
					stroke-width="2.5"
					fill="none"
					stroke-linecap="round"
				/>
				<circle cx="148" cy="113" r="14" fill="#CC1111" />
				<circle cx="144" cy="109" r="3.5" fill="rgba(255,255,255,0.18)" />

				<!-- Cherry 3 — BAD 🐛 -->
				<path
					d="M178,108 Q184,83 176,69"
					stroke="#2d6a27"
					stroke-width="2.5"
					fill="none"
					stroke-linecap="round"
				/>
				<circle cx="178" cy="116" r="14" fill="#881010" />
				<path
					d="M170,116 Q175,109 181,116 Q187,123 180,127"
					stroke="#7dca50"
					stroke-width="2.8"
					fill="none"
					stroke-linecap="round"
				/>

				<!-- Cherry 4 — GOOD -->
				<path
					d="M210,112 Q216,87 208,73"
					stroke="#2d6a27"
					stroke-width="2.5"
					fill="none"
					stroke-linecap="round"
				/>
				<circle cx="210" cy="120" r="13" fill="#CC1111" />
				<circle cx="206" cy="116" r="3" fill="rgba(255,255,255,0.18)" />

				<!-- Cherry 5 — BAD 🐛 -->
				<path
					d="M237,118 Q244,94 236,80"
					stroke="#2d6a27"
					stroke-width="2"
					fill="none"
					stroke-linecap="round"
				/>
				<circle cx="237" cy="126" r="12" fill="#881010" />
				<path
					d="M230,126 Q234,120 239,126 Q244,132 238,135"
					stroke="#7dca50"
					stroke-width="2.5"
					fill="none"
					stroke-linecap="round"
				/>

				<!-- Cherries inside basket (peeking above rim) -->
				<!-- Cherry 6 — GOOD, slightly inside -->
				<path
					d="M135,125 Q130,108 140,98"
					stroke="#2d6a27"
					stroke-width="2"
					fill="none"
					stroke-linecap="round"
				/>
				<circle cx="135" cy="131" r="11" fill="#CC1111" />

				<!-- Cherry 7 — BAD, slightly inside -->
				<path
					d="M197,120 Q203,103 195,93"
					stroke="#2d6a27"
					stroke-width="2"
					fill="none"
					stroke-linecap="round"
				/>
				<circle cx="197" cy="127" r="11" fill="#881010" />
				<path
					d="M192,127 Q195,122 199,127 Q203,132 198,135"
					stroke="#7dca50"
					stroke-width="2"
					fill="none"
					stroke-linecap="round"
				/>

				<!-- Labels -->
				<text
					x="60"
					y="286"
					fill="#73c37c"
					font-size="18"
					font-family="Inter, sans-serif"
					font-weight="600">🍒 ×50 good</text
				>
				<text
					x="200"
					y="286"
					fill="#ff6b6b"
					font-size="18"
					font-family="Inter, sans-serif"
					font-weight="600">🐛 ×50 wormy</text
				>
			</svg>
		</div>
	</div>
</div>

<style>
	.slide-4 {
		background: var(--dark);
	}

	.body {
		flex: 1;
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 48px;
		align-items: center;
	}

	.story {
		display: flex;
		flex-direction: column;
		gap: 24px;
	}

	.story-lead {
		font-size: var(--fsz-m);
		line-height: 1.6;
		color: #c8c6c5;
	}

	.story-lead strong {
		color: var(--light);
		font-weight: 700;
	}

	.stats-row {
		display: flex;
		gap: 16px;
	}

	.stat {
		flex: 1;
		display: flex;
		flex-direction: column;
		gap: 4px;
		padding: 16px 20px;
		border-radius: 10px;
	}

	.stat.good {
		background: rgba(115, 195, 124, 0.1);
		border: 1px solid rgba(115, 195, 124, 0.25);
	}

	.stat.bad {
		background: rgba(204, 17, 17, 0.1);
		border: 1px solid rgba(204, 17, 17, 0.25);
	}

	.stat-num {
		font-size: var(--fsz-xl);
		font-weight: 800;
		line-height: 1;
	}

	.stat.good .stat-num {
		color: var(--green);
	}
	.stat.bad .stat-num {
		color: #ff6b6b;
	}

	.stat-label {
		font-size: var(--fsz-m);
		color: #848484;
	}

	.goal-box {
		display: flex;
		align-items: center;
		gap: 16px;
		background: rgba(250, 198, 31, 0.08);
		border: 1px solid rgba(250, 198, 31, 0.25);
		border-radius: 12px;
		padding: 18px 22px;
	}

	.goal-icon {
		font-size: var(--fsz-xl);
	}

	.goal-title {
		font-size: var(--fsz-s);
		font-weight: 700;
		letter-spacing: 0.1em;
		text-transform: uppercase;
		color: var(--yellow);
		margin-bottom: 4px;
	}

	.goal-text {
		font-size: var(--fsz-m);
		color: var(--light);
	}

	.goal-text strong {
		color: var(--yellow);
		font-weight: 700;
	}

	.question {
		font-size: var(--fsz-m);
		color: var(--blue);
		font-style: italic;
	}

	.illustration {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.basket-svg {
		width: 100%;
		max-width: 360px;
		filter: drop-shadow(0 8px 32px rgba(160, 112, 64, 0.25));
	}
</style>
