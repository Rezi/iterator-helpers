<script lang="ts">
	const useWhen = [
		{
			title: 'Large or infinite datasets',
			desc: 'When loading everything into memory is expensive or impossible.'
		},
		{
			title: 'Early termination matters',
			desc: 'You only need the first N results that satisfy a condition.'
		},
		{
			title: 'Chained transformations',
			desc: 'Multiple map/filter steps — no intermediate arrays needed.'
		},
		{
			title: 'Streaming or real-time data',
			desc: 'Generators feeding data as it arrives from a network or sensor.'
		},
		{
			title: 'Memory-sensitive environments',
			desc: 'Edge functions, embedded contexts, or large data pipelines.'
		}
	];

	const stickWith = [
		{
			title: 'Small, known-size arrays',
			desc: 'Overhead of iterator protocol outweighs laziness for tiny data.'
		},
		{
			title: 'Random access needed',
			desc: 'Array indexing (arr[i]) is not possible with iterators.'
		},
		{
			title: 'Multiple passes required',
			desc: 'Iterators are single-pass; arrays can be re-iterated freely.'
		},
		{
			title: 'Older environment support',
			desc: 'Requires Node 22+ / modern browsers; polyfills add complexity.'
		},
		{
			title: 'Team unfamiliar with iterators',
			desc: 'Array methods are more widely understood — readability wins.'
		}
	];
</script>

<div class="slide slide-10">
	<div class="slide-heading">When to <span class="accent">Use</span> Them</div>
	<div class="heading-bar"></div>

	<div class="body">
		<div class="column use-col">
			<div class="col-title">
				<span class="col-icon">⚡</span>
				<span>Reach for Iterator Helpers when…</span>
			</div>
			{#each useWhen as item}
				<div class="item use-item">
					<span class="item-icon">✓</span>
					<div>
						<div class="item-title">{item.title}</div>
						<div class="item-desc">{item.desc}</div>
					</div>
				</div>
			{/each}
		</div>

		<div class="divider-col" aria-hidden="true">
			<div class="vline"></div>
			<div class="vs-circle">vs</div>
			<div class="vline"></div>
		</div>

		<div class="column array-col">
			<div class="col-title">
				<span class="col-icon">📋</span>
				<span>Stick with Array methods when…</span>
			</div>
			{#each stickWith as item}
				<div class="item array-item">
					<span class="item-icon arr-icon">→</span>
					<div>
						<div class="item-title">{item.title}</div>
						<div class="item-desc">{item.desc}</div>
					</div>
				</div>
			{/each}
		</div>
	</div>

	<div class="bottom-rule">
		<span class="rule-icon">🍒</span>
		<em
			>Rule of thumb: if you'd stop checking cherries the moment you have enough good ones — use
			iterator helpers.</em
		>
	</div>
</div>

<style>
	.slide-10 {
		background: var(--dark);
	}

	.body {
		flex: 1;
		display: grid;
		grid-template-columns: 1fr 52px 1fr;
		gap: 0;
		align-items: start;
	}

	.column {
		display: flex;
		flex-direction: column;
		gap: 10px;
		padding: 0 8px;
	}

	.col-title {
		display: flex;
		align-items: center;
		gap: 10px;
		font-size: var(--fsz-s);
		font-weight: 700;
		margin-bottom: 6px;
		padding-bottom: 12px;
		border-bottom: 1px solid rgba(255, 255, 255, 0.07);
	}

	.use-col .col-title {
		color: var(--yellow);
	}
	.array-col .col-title {
		color: #b0b0c0;
	}

	.col-icon {
		font-size: var(--fsz-m);
	}

	.item {
		display: flex;
		align-items: flex-start;
		gap: 12px;
		padding: 10px 14px;
		border-radius: 9px;
	}

	.use-item {
		background: rgba(250, 198, 31, 0.05);
		border: 1px solid rgba(250, 198, 31, 0.12);
	}

	.array-item {
		background: rgba(255, 255, 255, 0.03);
		border: 1px solid rgba(255, 255, 255, 0.06);
	}

	.item-icon {
		font-size: var(--fsz-s);
		font-weight: 800;
		color: var(--yellow);
		flex-shrink: 0;
		margin-top: 1px;
		line-height: 1.4;
	}

	.arr-icon {
		color: var(--gray);
	}

	.item-title {
		font-size: var(--fsz-s);
		font-weight: 700;
		color: var(--light);
		margin-bottom: 2px;
	}

	.item-desc {
		font-size: var(--fsz-s);
		color: #848484;
		line-height: 1.45;
	}

	.divider-col {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 0;
		padding-top: 40px;
	}

	.vline {
		width: 1px;
		flex: 1;
		background: rgba(255, 255, 255, 0.08);
	}

	.vs-circle {
		width: 32px;
		height: 32px;
		border-radius: 50%;
		border: 1px solid rgba(255, 255, 255, 0.1);
		background: rgba(255, 255, 255, 0.04);
		color: var(--gray);
		font-size: var(--fsz-s);
		font-weight: 700;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-shrink: 0;
	}

	.bottom-rule {
		display: flex;
		align-items: center;
		gap: 12px;
		font-size: var(--fsz-s);
		color: #848484;
		font-style: italic;
		margin-top: 8px;
		padding-top: 14px;
		margin-bottom: 1rem;
		border-top: 1px solid rgba(255, 255, 255, 0.06);
	}

	.rule-icon {
		font-size: var(--fsz-m);
		flex-shrink: 0;
	}
</style>
