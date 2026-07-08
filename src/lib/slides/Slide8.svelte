<div class="slide slide-8">
	<div class="slide-heading">Using with <span class="accent">Generators</span></div>
	<div class="heading-bar"></div>

	<div class="body">
		<div class="left">
			<p class="intro-text">
				Generator functions return an iterator. Iterator helpers chain directly onto them, making
				infinite sequences and lazy pipelines effortless.
			</p>

			<div class="steps">
				<div class="step">
					<div class="step-num">1</div>
					<div class="step-text">
						<strong>Define</strong> a generator with <code>function*</code> and <code>yield</code>
					</div>
				</div>
				<div class="step">
					<div class="step-num">2</div>
					<div class="step-text">
						<strong>Call</strong> the generator — it returns an iterator object
					</div>
				</div>
				<div class="step">
					<div class="step-num">3</div>
					<div class="step-text">
						<strong>Chain</strong> iterator helpers directly on the result
					</div>
				</div>
			</div>

			<div class="compat-note">
				<span class="compat-icon">📦</span>
				<span>Works with any iterable via <code>Iterator.from(iterable)</code></span>
			</div>
		</div>

		<div class="right">
			<div class="code-label-row">
				<span class="code-label-tag">Example — Infinite sequence with generators</span>
			</div>
			<pre class="code-block"><code
					><span class="cmt">// 1. Infinite generator — never ends on its own</span>
<span class="kw">function</span>* <span class="fn">naturals</span>(start = <span class="num">1</span
					>) {`{`}
  <span class="kw">while</span> (<span class="kw">true</span>) <span class="kw">yield</span
					> start++;
{`}`}
<span class="cmt">// 2. Chain iterator helpers onto it</span>
<span class="kw">const</span> firstTenEvenSquares = <span class="fn">naturals</span>()
  .<span class="prop">filter</span>(n => n % <span class="num">2</span> === <span class="num"
						>0</span
					>)  <span class="cmt">// keep only even numbers</span>
  .<span class="prop">map</span>(n => n ** <span class="num">2</span>)           <span class="cmt"
						>// square them</span
					>
  .<span class="prop">take</span>(<span class="num">10</span>)                    <span class="cmt"
						>// stop after 10</span
					>
  .<span class="prop">toArray</span>();
<span class="cmt">// → [4, 16, 36, 64, 100, 144, 196, 256, 324, 400]</span>
<span class="cmt">// 3. Iterator.from() for non-array iterables</span>
<span class="kw">const</span> fromSet = <span class="cls">Iterator</span>.<span class="fn"
						>from</span
					>(<span class="kw">new</span> <span class="cls">Set</span>([<span class="num">1</span
					>, <span class="num">2</span>, <span class="num">3</span>, <span class="num">4</span>]))
  .<span class="prop">filter</span>(x => x % <span class="num">2</span> !== <span class="num"
						>0</span
					>)
  .<span class="prop">toArray</span>();</code
				></pre>

			<div class="highlight-box">
				<span class="hl-icon">🔑</span>
				<div>
					<div class="hl-title">Key insight</div>
					<div class="hl-text">
						The generator produces values <em>one at a time</em>, and <code>.take(10)</code>
						stops pulling after 10 are collected — so the infinite loop never runs forever.
					</div>
				</div>
			</div>
		</div>
	</div>
</div>

<style>
	.slide-8 {
		background: var(--dark);
	}

	.body {
		flex: 1;
		display: grid;
		grid-template-columns: 1fr 1.6fr;
		gap: 44px;
		align-items: start;
	}

	.left {
		display: flex;
		flex-direction: column;
		gap: 22px;
	}

	.intro-text {
		font-size: var(--fsz-s);
		color: #b0b0c0;
		line-height: 1.7;
	}

	.steps {
		display: flex;
		flex-direction: column;
		gap: 12px;
	}

	.step {
		display: flex;
		align-items: flex-start;
		gap: 12px;
	}

	.step-num {
		width: 26px;
		height: 26px;
		border-radius: 50%;
		background: rgba(250, 198, 31, 0.15);
		border: 1px solid rgba(250, 198, 31, 0.35);
		color: var(--yellow);
		font-size: var(--fsz-s);
		font-weight: 800;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-shrink: 0;
		margin-top: 1px;
	}

	.step-text {
		font-size: var(--fsz-s);
		color: #b0b0c0;
		line-height: 1.5;
	}

	.step-text strong {
		color: var(--light);
	}

	.step-text code {
		background: rgba(255, 255, 255, 0.06);
		padding: 1px 6px;
		border-radius: 4px;
		font-size: var(--fsz-s);
		color: var(--yellow);
		font-family: 'Fira Code', monospace;
	}

	.compat-note {
		display: flex;
		align-items: center;
		gap: 10px;
		font-size: var(--fsz-s);
		color: var(--gray);
		background: rgba(255, 255, 255, 0.03);
		border: 1px solid rgba(255, 255, 255, 0.07);
		border-radius: 8px;
		padding: 10px 14px;
	}

	.compat-note code {
		color: var(--blue);
		font-family: 'Fira Code', monospace;
		font-size: var(--fsz-s);
		background: rgba(94, 202, 231, 0.08);
		padding: 1px 5px;
		border-radius: 3px;
	}

	.right {
		display: flex;
		flex-direction: column;
		gap: 12px;
	}

	.code-label-row {
		display: flex;
		align-items: center;
	}

	.code-label-tag {
		font-size: var(--fsz-s);
		font-weight: 600;
		letter-spacing: 0.08em;
		text-transform: uppercase;
		color: var(--gray);
	}

	.highlight-box {
		display: flex;
		align-items: flex-start;
		gap: 12px;
		background: rgba(115, 195, 124, 0.07);
		border: 1px solid rgba(115, 195, 124, 0.2);
		border-radius: 10px;
		padding: 14px 16px;
	}

	.hl-icon {
		font-size: var(--fsz-m);
		flex-shrink: 0;
	}

	.hl-title {
		font-size: var(--fsz-s);
		font-weight: 700;
		color: var(--green);
		text-transform: uppercase;
		letter-spacing: 0.07em;
		margin-bottom: 4px;
	}

	.hl-text {
		font-size: var(--fsz-s);
		color: #b0b0c0;
		line-height: 1.6;
	}

	.hl-text code {
		color: var(--yellow);
		font-family: 'Fira Code', monospace;
		font-size: var(--fsz-s);
		background: rgba(250, 198, 31, 0.08);
		padding: 1px 5px;
		border-radius: 3px;
	}
</style>
