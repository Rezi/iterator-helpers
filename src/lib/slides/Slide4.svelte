<div class="slide slide-4">
	<div class="slide-heading">Three Ways to <span class="accent">Pick Cherries</span></div>
	<div class="heading-bar"></div>

	<div class="approaches">
		<!-- Human approach -->
		<div class="approach human">
			<div class="approach-header">
				<span class="approach-icon">🧑</span>
				<div>
					<div class="approach-label">The Human</div>
					<div class="approach-title">One by one</div>
				</div>
			</div>
			<div class="cherry-row">
				{#each Array(7) as _, i}
					<div
						class="cherry-check"
						class:bad={i === 1 || i === 3}
						class:good={i !== 1 && i !== 3 && i < 5}
						class:stop={i >= 5}
					>
						<svg viewBox="0 0 32 38" width="32" height="38">
							<path
								d="M16,13 Q12,4 20,0"
								stroke="#2d6a27"
								stroke-width="2"
								fill="none"
								stroke-linecap="round"
							/>
							<circle
								cx="16"
								cy="22"
								r="11"
								fill={i === 1 || i === 3 ? '#881010' : i >= 5 ? '#2a2a40' : '#CC1111'}
							/>
							{#if i === 1 || i === 3}
								<path
									d="M10,22 Q13,17 17,22 Q21,27 16,30"
									stroke="#7dca50"
									stroke-width="2.2"
									fill="none"
									stroke-linecap="round"
								/>
							{/if}
							{#if i !== 1 && i !== 3 && i < 5}
								<text x="9" y="26" fill="white" font-size="10" font-family="sans-serif">✓</text>
							{/if}
							{#if i >= 5}
								<text x="10" y="26" fill="#444" font-size="9" font-family="sans-serif">···</text>
							{/if}
						</svg>
					</div>
				{/each}
			</div>
			<div class="approach-verdict">
				Checks 1 by 1 → <strong>stops at 3rd good one</strong>
				<br />Checked maybe <span class="hl-green">5–8 cherries total</span>
			</div>
		</div>

		<!-- Array approach -->
		<div class="approach array-way">
			<div class="approach-header">
				<span class="approach-icon">📋</span>
				<div>
					<div class="approach-label">The Programmer (Arrays)</div>
					<div class="approach-title">Filter everything first</div>
				</div>
			</div>
			<div class="array-visual">
				<div class="array-step">
					<div class="step-label">Step 1: filter() ALL 100</div>
					<div class="cherry-mini-row">
						{#each Array(10) as _, i}
							<div class="mini-cherry" class:bad-mini={i === 1 || i === 4 || i === 7}></div>
						{/each}
						<span class="ellipsis">…×100</span>
					</div>
				</div>
				<div class="arrow">↓</div>
				<div class="array-step">
					<div class="step-label">Step 2: .slice(0, 3)</div>
					<div class="cherry-mini-row">
						<div class="mini-cherry"></div>
						<div class="mini-cherry"></div>
						<div class="mini-cherry"></div>
					</div>
				</div>
			</div>
			<div class="approach-verdict warning">
				Processed <span class="hl-red">all 100 cherries</span> even though we
				<br />only needed 3. Wasted work!
			</div>
		</div>

		<!-- Iterator helpers approach -->
		<div class="approach iterator-way">
			<div class="approach-header">
				<span class="approach-icon">⚡</span>
				<div>
					<div class="approach-label">Iterator Helpers</div>
					<div class="approach-title">Think like a human</div>
				</div>
			</div>
			<div class="cherry-row">
				{#each Array(7) as _, i}
					<div
						class="cherry-check"
						class:bad={i === 1 || i === 3}
						class:good={i !== 1 && i !== 3 && i < 5}
						class:stop={i >= 5}
					>
						<svg viewBox="0 0 32 38" width="32" height="38">
							<path
								d="M16,13 Q12,4 20,0"
								stroke="#2d6a27"
								stroke-width="2"
								fill="none"
								stroke-linecap="round"
							/>
							<circle
								cx="16"
								cy="22"
								r="11"
								fill={i === 1 || i === 3 ? '#881010' : i >= 5 ? '#2a2a40' : '#CC1111'}
							/>
							{#if i === 1 || i === 3}
								<path
									d="M10,22 Q13,17 17,22 Q21,27 16,30"
									stroke="#7dca50"
									stroke-width="2.2"
									fill="none"
									stroke-linecap="round"
								/>
							{/if}
							{#if i !== 1 && i !== 3 && i < 5}
								<text x="9" y="26" fill="white" font-size="16" font-family="sans-serif">✓</text>
							{/if}
							{#if i >= 5}
								<text x="10" y="26" fill="#444" font-size="14" font-family="sans-serif">···</text>
							{/if}
						</svg>
					</div>
				{/each}
			</div>
			<div class="approach-verdict good-verdict">
				Lazy, just like the human →
				<strong>stops the moment it has 3 good ones</strong>
				<br />Never touches the rest <span class="hl-green">🎉</span>
			</div>
		</div>
	</div>
</div>

<style>
	.slide-4 {
		background: var(--dark);
	}

	.approaches {
		flex: 1;
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 16px;
		align-items: start;
	}

	.approach {
		border-radius: 14px;
		padding: 22px 20px;
		display: flex;
		flex-direction: column;
		gap: 16px;
		height: 100%;
	}

	.human {
		background: rgba(115, 195, 124, 0.07);
		border: 1px solid rgba(115, 195, 124, 0.2);
	}

	.array-way {
		background: rgba(255, 107, 107, 0.07);
		border: 1px solid rgba(255, 107, 107, 0.2);
	}

	.iterator-way {
		background: rgba(250, 198, 31, 0.07);
		border: 1.5px solid rgba(250, 198, 31, 0.3);
	}

	.approach-header {
		display: flex;
		align-items: center;
		gap: 12px;
	}

	.approach-icon {
		font-size: var(--fsz-lg);
	}

	.approach-label {
		font-size: var(--fsz-s);
		font-weight: 700;
		letter-spacing: 0.1em;
		text-transform: uppercase;
		color: var(--gray);
	}

	.approach-title {
		font-size: var(--fsz-s);
		font-weight: 700;
		color: var(--light);
	}

	.cherry-row {
		display: flex;
		flex-wrap: wrap;
		gap: 4px;
		align-items: center;
	}

	.array-visual {
		display: flex;
		flex-direction: column;
		gap: 8px;
		align-items: flex-start;
	}

	.array-step {
		display: flex;
		flex-direction: column;
		gap: 6px;
	}

	.step-label {
		font-size: var(--fsz-s);
		font-weight: 600;
		letter-spacing: 0.06em;
		color: var(--gray);
		text-transform: uppercase;
	}

	.cherry-mini-row {
		display: flex;
		flex-wrap: wrap;
		gap: 3px;
		align-items: center;
	}

	.mini-cherry {
		width: 14px;
		height: 14px;
		border-radius: 50%;
		background: #cc1111;
	}

	.bad-mini {
		background: #881010;
	}

	.ellipsis {
		font-size: var(--fsz-s);
		color: var(--gray);
		margin-left: 4px;
	}

	.arrow {
		font-size: var(--fsz-m);
		color: var(--gray);
		padding-left: 8px;
	}

	.approach-verdict {
		font-size: var(--fsz-s);
		line-height: 1.6;
		color: #b0b0c0;
		margin-top: auto;
		padding-top: 8px;
		border-top: 1px solid rgba(255, 255, 255, 0.06);
	}

	.approach-verdict strong {
		color: var(--light);
	}

	.approach-verdict.warning .hl-red {
		color: #ff6b6b;
		font-weight: 700;
	}

	.good-verdict .hl-green,
	.approach-verdict .hl-green {
		color: var(--green);
		font-weight: 700;
	}
</style>
