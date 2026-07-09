<div class="slide slide-3">
	<div class="slide-heading">What Are <span class="accent">Iterator Helpers?</span></div>
	<div class="heading-bar"></div>

	<div class="body">
		<div class="cards">
			<div class="card">
				<div class="card-icon">🔗</div>
				<div class="card-title">Built-in Prototype Methods</div>
				<p class="card-text">
					New methods directly on the <code>Iterator</code> prototype, standardised in
					<strong>ECMAScript 2025</strong>. Available in Node.js 22+ and modern browsers.
				</p>
			</div>
			<div class="card">
				<div class="card-icon">💤</div>
				<div class="card-title">Lazy Evaluation</div>
				<p class="card-text">
					Each element is processed <strong>only when it is actually needed</strong>. Nothing runs
					until you consume the iterator — unlike array methods which run eagerly over everything.
				</p>
			</div>
			<div class="card">
				<div class="card-icon">⚡</div>
				<div class="card-title">Memory Efficient</div>
				<p class="card-text">
					No intermediate arrays are created during chained operations. Elements flow through the
					pipeline one-by-one, enabling <strong>early termination</strong> and infinite sequences.
				</p>
			</div>
		</div>

		<div class="code-preview">
			<div class="code-label">Quick look</div>
			<pre class="code-block"><code
					><span class="cmt">// Turn any iterable into an iterator</span>
<span class="kw">const</span> result = [<span class="num">1</span>, <span class="num">2</span
					>, <span class="num">3</span>, <span class="num">4</span>, <span class="num">5</span
					>].<span class="fn">values</span>()
  .<span class="prop">filter</span>(x => x % <span class="num">2</span> === <span class="num"
						>0</span
					>)  <span class="cmt">// lazy — nothing runs yet</span>
  .<span class="prop">map</span>(x => x * x)            <span class="cmt"
						>// lazy — still nothing</span
					>
  .<span class="prop">take</span>(<span class="num">2</span>)                    <span class="cmt"
						>// lazy — still nothing</span
					>
  .<span class="prop">toArray</span>();                  <span class="cmt"
						>// NOW it runs — pulls only what's needed</span
					>
<span class="cmt">// → [4, 16]</span></code
				></pre>
		</div>
	</div>
</div>

<style>
	.slide-3 {
		background: var(--dark);
	}

	.body {
		flex: 1;
		display: flex;
		flex-direction: column;
		gap: 28px;
	}

	.cards {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 18px;
	}

	.card {
		background: rgba(255, 255, 255, 0.03);
		border: 1px solid rgba(255, 255, 255, 0.07);
		border-radius: 12px;
		padding: 24px 22px;
		display: flex;
		flex-direction: column;
		gap: 10px;
		transition: border-color 0.2s;
	}

	.card:hover {
		border-color: rgba(250, 198, 31, 0.2);
	}

	.card-icon {
		font-size: var(--fsz-lg);
		line-height: 1;
	}

	.card-title {
		font-size: var(--fsz-m);
		font-weight: 700;
		color: var(--yellow);
	}

	.card-text {
		font-size: var(--fsz-m);
		color: #b0b0c0;
		line-height: 1.65;
	}

	.card-text strong {
		color: var(--light);
	}

	.code-preview {
		display: flex;
		flex-direction: column;
		gap: 8px;
	}

	.code-label {
		font-size: var(--fsz-s);
		font-weight: 600;
		letter-spacing: 0.1em;
		text-transform: uppercase;
		color: var(--gray);
	}
</style>
