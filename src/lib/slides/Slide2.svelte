<div class="slide slide-2">
	<div class="slide-heading">What Is an <span class="accent">Iterator?</span></div>
	<div class="heading-bar"></div>

	<div class="body">
		<!-- Left: explanation -->
		<div class="explain">
			<p class="lead">
				An <strong>iterator</strong> is any object that knows how to produce a
				<strong>sequence of values, one at a time</strong> — it just has to follow a simple protocol.
			</p>

			<div class="protocol">
				<div class="proto-row">
					<code class="proto-key">[Symbol.iterator]()</code>
					<p class="proto-text">
						Makes an object <strong>iterable</strong>. Returns an iterator — usable in
						<code>for…of</code> and spread <code>[...x]</code>.
					</p>
				</div>
				<div class="proto-row">
					<code class="proto-key">.next()</code>
					<p class="proto-text">
						Called on the iterator to pull the next result:
						<code>&#123; value, done &#125;</code>. When <code>done</code> is <code>true</code>, the
						sequence is over.
					</p>
				</div>
			</div>

			<div class="builtins">
				<div class="builtins-label">Built-in iterables</div>
				<div class="chips">
					<span class="chip">🔤 String</span>
					<span class="chip">📦 Array</span>
					<span class="chip">🗺️ Map</span>
					<span class="chip">🎯 Set</span>
					<span class="chip">🌐 DOM collections</span>
					<span class="chip">⚙️ Generators</span>
				</div>
			</div>
		</div>

		<!-- Right: minimal example -->
		<div class="code-preview">
			<div class="code-label">A minimal iterable</div>
			<pre class="code-block"><code
					><span class="cmt">// Counts from 1 to 3, lazily</span>
<span class="kw">const</span> range = &#123;
  [<span class="cls">Symbol</span>.<span class="prop">iterator</span>]() &#123;
    <span class="kw">let</span> n = <span class="num">1</span>;
    <span class="kw">return</span> &#123;
      <span class="fn">next</span>() &#123;
        <span class="kw">return</span> n &lt;= <span class="num">3</span>
          ? &#123; value: n++, done: <span class="kw">false</span> &#125;
          : &#123; value: <span class="kw">undefined</span>, done: <span class="kw">true</span
					> &#125;;
      &#125;
    &#125;;
  &#125;
&#125;;

<span class="kw">for</span> (<span class="kw">const</span> x <span class="kw">of</span> range) <span
						class="fn">console</span
					>.<span class="prop">log</span>(x);
<span class="cmt">// → 1, 2, 3</span>
[...range];  <span class="cmt">// → [1, 2, 3]</span></code
				></pre>
		</div>
	</div>
</div>

<style>
	.slide-2 {
		background: var(--dark);
	}

	.body {
		flex: 1;
		display: grid;
		grid-template-columns: 1fr 1.05fr;
		gap: 48px;
		align-items: center;
	}

	.explain {
		display: flex;
		flex-direction: column;
		gap: 26px;
	}

	.lead {
		font-size: var(--fsz-m);
		line-height: 1.6;
		color: #c8c6c5;
	}

	.lead strong {
		color: var(--light);
		font-weight: 700;
	}

	.protocol {
		display: flex;
		flex-direction: column;
		gap: 16px;
	}

	.proto-row {
		display: flex;
		flex-direction: column;
		gap: 8px;
		background: rgba(255, 255, 255, 0.03);
		border: 1px solid rgba(255, 255, 255, 0.07);
		border-left: 3px solid var(--yellow);
		border-radius: 10px;
		padding: 16px 20px;
	}

	.proto-key {
		font-size: var(--fsz-m);
		font-weight: 700;
		color: var(--yellow);
	}

	.proto-text {
		font-size: var(--fsz-s);
		color: #b0b0c0;
		line-height: 1.6;
	}

	.proto-text code,
	.lead code {
		color: var(--blue);
		background: rgba(94, 202, 231, 0.08);
		border-radius: 4px;
		padding: 1px 6px;
	}

	.proto-text strong {
		color: var(--light);
	}

	.note-box {
		display: flex;
		align-items: center;
		gap: 14px;
		background: rgba(250, 198, 31, 0.08);
		border: 1px solid rgba(250, 198, 31, 0.25);
		border-radius: 12px;
		padding: 16px 20px;
		font-size: var(--fsz-s);
		color: #c0c0d0;
		line-height: 1.55;
	}

	.note-box strong {
		color: var(--yellow);
	}

	.note-box code {
		color: var(--blue);
	}

	.note-icon {
		font-size: var(--fsz-l);
		line-height: 1;
	}

	.builtins {
		display: flex;
		flex-direction: column;
		gap: 12px;
	}

	.builtins-label {
		font-size: var(--fsz-s);
		font-weight: 600;
		letter-spacing: 0.1em;
		text-transform: uppercase;
		color: var(--gray);
	}

	.chips {
		display: flex;
		flex-wrap: wrap;
		gap: 10px;
	}

	.chip {
		display: inline-flex;
		align-items: center;
		gap: 7px;
		background: rgba(94, 202, 231, 0.08);
		border: 1px solid rgba(94, 202, 231, 0.25);
		border-radius: 20px;
		padding: 7px 15px;
		font-size: var(--fsz-s);
		font-weight: 600;
		color: var(--blue);
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
