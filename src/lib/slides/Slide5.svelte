<div class="slide slide-5">
	<div class="slide-heading">Iterator Helpers in <span class="accent">Action</span></div>
	<div class="heading-bar"></div>

	<div class="body">
		<!-- Code comparison -->
		<div class="codes">
			<div class="code-panel old">
				<div class="code-panel-header">
					<span class="code-badge array-badge">Array methods — Eager 😓</span>
				</div>
				<pre class="code-block"><code
						><span class="kw">const</span> goodCherries = cherries
  .<span class="prop">filter</span>(c => !c.<span class="fn">hasWorm</span>())  <span class="cmt"
							>// ← checks ALL 100</span
						>
  .<span class="prop">slice</span>(<span class="num">0</span>, <span class="num">3</span
						>);               <span class="cmt">// ← then takes 3</span>

<span class="cmt">// Created a full filtered array</span>
<span class="cmt">// even though we only need 3!</span></code
					></pre>
				<div class="annotation danger">
					<span class="ann-icon">⚠️</span>
					<span>Processes <strong>all 100</strong> cherries</span>
				</div>
			</div>

			<div class="vs-divider">
				<span>vs</span>
			</div>

			<div class="code-panel new">
				<div class="code-panel-header">
					<span class="code-badge iter-badge">Iterator Helpers — Lazy ⚡</span>
				</div>
				<pre class="code-block"><code
						><span class="kw">const</span> goodCherries = cherries
  .<span class="fn">values</span>()               <span class="cmt">// get an iterator</span>
  .<span class="prop">filter</span>(c => !c.<span class="fn">hasWorm</span>())  <span class="cmt"
							>// lazy filter</span
						>
  .<span class="prop">take</span>(<span class="num">3</span>)               <span class="cmt"
							>// stop after 3 ✅</span
						>
  .<span class="prop">toArray</span>();             <span class="cmt">// consume now</span></code
					></pre>
				<div class="annotation success">
					<span class="ann-icon">✅</span>
					<span>Stops after finding <strong>3 good ones</strong></span>
				</div>
			</div>
		</div>

		<!-- Visual pipeline -->
		<div class="pipeline-section">
			<div class="pipeline-label">How the lazy pipeline flows</div>
			<div class="pipeline">
				<div class="basket-mini" title="100 cherries in the basket">
					<svg viewBox="0 0 80 70" width="72" height="63">
						<path d="M20,35 Q20,64 40,64 Q60,64 60,35 Z" fill="#A07040" />
						<path d="M22,44 Q40,49 58,44" stroke="#7A5030" stroke-width="2" fill="none" />
						<path d="M21,54 Q40,60 59,54" stroke="#7A5030" stroke-width="2" fill="none" />
						<ellipse cx="40" cy="34" rx="21" ry="5.5" fill="#C09050" />
						<path
							d="M25,32 Q40,12 55,32"
							stroke="#9B7040"
							stroke-width="5"
							fill="none"
							stroke-linecap="round"
						/>
						<circle cx="32" cy="28" r="7" fill="#CC1111" />
						<circle cx="47" cy="26" r="6.5" fill="#881010" />
						<path
							d="M44,26 Q46,23 49,26 Q52,29 48,31"
							stroke="#7dca50"
							stroke-width="1.8"
							fill="none"
							stroke-linecap="round"
						/>
					</svg>
					<span class="pl-label">100 cherries</span>
				</div>

				<div class="pipeline-arrow">→</div>

				<div class="pl-step filter-step">
					<span class="pl-method">.filter()</span>
					<span class="pl-desc">skip wormies</span>
				</div>

				<div class="pipeline-arrow">→</div>

				<div class="pl-step take-step">
					<span class="pl-method">.take(3)</span>
					<span class="pl-desc">stop at 3</span>
				</div>

				<div class="pipeline-arrow">→</div>

				<div class="pl-step result-step">
					<div class="cherry-trio">
						{#each [1, 2, 3] as _}
							<svg viewBox="0 0 28 32" width="26" height="30">
								<path
									d="M14,10 Q10,2 18,0"
									stroke="#2d6a27"
									stroke-width="2"
									fill="none"
									stroke-linecap="round"
								/>
								<circle cx="14" cy="20" r="10" fill="#CC1111" />
								<circle cx="11" cy="17" r="2.5" fill="rgba(255,255,255,0.2)" />
							</svg>
						{/each}
					</div>
					<span class="pl-label">3 good ones</span>
				</div>
			</div>
			<div class="pipeline-note">
				Only the cherries that actually <em>pass through</em> the filter are evaluated — everything else
				stays untouched in the basket.
			</div>
		</div>
	</div>
</div>

<style>
	.slide-5 {
		background: var(--dark);
	}

	.body {
		flex: 1;
		display: flex;
		flex-direction: column;
		gap: 20px;
	}

	.codes {
		display: flex;
		gap: 16px;
		align-items: flex-start;
	}

	.code-panel {
		flex: 1;
		display: flex;
		flex-direction: column;
		gap: 10px;
	}

	.code-panel-header {
		display: flex;
		align-items: center;
	}

	.code-badge {
		font-size: var(--fsz-s);
		font-weight: 700;
		padding: 4px 12px;
		border-radius: 20px;
	}

	.array-badge {
		background: rgba(255, 107, 107, 0.12);
		color: #ff9090;
		border: 1px solid rgba(255, 107, 107, 0.25);
	}

	.iter-badge {
		background: rgba(250, 198, 31, 0.12);
		color: var(--yellow);
		border: 1px solid rgba(250, 198, 31, 0.3);
	}

	.annotation {
		display: flex;
		align-items: center;
		gap: 8px;
		font-size: var(--fsz-s);
		padding: 8px 14px;
		border-radius: 8px;
	}

	.annotation.danger {
		background: rgba(255, 107, 107, 0.08);
		border: 1px solid rgba(255, 107, 107, 0.2);
		color: #ff9090;
	}

	.annotation.success {
		background: rgba(115, 195, 124, 0.08);
		border: 1px solid rgba(115, 195, 124, 0.25);
		color: var(--green);
	}

	.annotation strong {
		color: inherit;
	}

	.vs-divider {
		display: flex;
		align-items: center;
		justify-content: center;
		width: 40px;
		flex-shrink: 0;
		padding-top: 30px;
	}

	.vs-divider span {
		font-size: var(--fsz-s);
		font-weight: 700;
		color: var(--gray);
		background: rgba(255, 255, 255, 0.05);
		border-radius: 50%;
		width: 32px;
		height: 32px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	/* Pipeline */
	.pipeline-section {
		background: rgba(255, 255, 255, 0.02);
		border: 1px solid rgba(255, 255, 255, 0.06);
		border-radius: 12px;
		padding: 16px 22px;
		display: flex;
		flex-direction: column;
		gap: 12px;
	}

	.pipeline-label {
		font-size: var(--fsz-s);
		font-weight: 700;
		letter-spacing: 0.1em;
		text-transform: uppercase;
		color: var(--gray);
	}

	.pipeline {
		display: flex;
		align-items: center;
		gap: 12px;
	}

	.basket-mini {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 4px;
	}

	.pipeline-arrow {
		font-size: var(--fsz-m);
		color: var(--gray);
		flex-shrink: 0;
	}

	.pl-step {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 4px;
		padding: 10px 16px;
		border-radius: 10px;
		flex-shrink: 0;
	}

	.filter-step {
		background: rgba(94, 202, 231, 0.1);
		border: 1px solid rgba(94, 202, 231, 0.2);
	}

	.take-step {
		background: rgba(250, 198, 31, 0.1);
		border: 1px solid rgba(250, 198, 31, 0.25);
	}

	.result-step {
		background: rgba(115, 195, 124, 0.1);
		border: 1px solid rgba(115, 195, 124, 0.25);
		padding: 10px 20px;
	}

	.pl-method {
		font-family: 'Fira Code', monospace;
		font-size: var(--fsz-s);
		font-weight: 700;
		color: var(--yellow);
	}

	.take-step .pl-method {
		color: var(--yellow);
	}

	.filter-step .pl-method {
		color: var(--blue);
	}

	.pl-desc {
		font-size: var(--fsz-s);
		color: var(--gray);
	}

	.pl-label {
		font-size: var(--fsz-s);
		color: var(--gray);
	}

	.cherry-trio {
		display: flex;
		gap: 2px;
	}

	.pipeline-note {
		font-size: var(--fsz-s);
		color: #848484;
		font-style: italic;
	}
</style>
