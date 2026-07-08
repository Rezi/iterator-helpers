<script lang="ts">
	const methods = [
		{
			name: '.map(fn)',
			desc: 'Transform each element',
			example: '.map(x => x * 2)',
			color: '#fac61f'
		},
		{
			name: '.filter(fn)',
			desc: 'Keep elements that match',
			example: '.filter(x => x > 0)',
			color: '#5ecae7'
		},
		{
			name: '.take(n)',
			desc: 'Yield first n elements, then stop',
			example: '.take(3)',
			color: '#73c37c'
		},
		{ name: '.drop(n)', desc: 'Skip first n elements', example: '.drop(10)', color: '#c792ea' },
		{
			name: '.flatMap(fn)',
			desc: 'Map then flatten iterables',
			example: '.flatMap(x => [x, x])',
			color: '#f78c6c'
		},
		{
			name: '.reduce(fn, acc)',
			desc: 'Aggregate into a single value',
			example: '.reduce((a,b) => a+b, 0)',
			color: '#fac61f'
		},
		{
			name: '.some(fn)',
			desc: 'True if any element matches',
			example: '.some(x => x < 0)',
			color: '#5ecae7'
		},
		{
			name: '.every(fn)',
			desc: 'True if all elements match',
			example: '.every(x => x > 0)',
			color: '#73c37c'
		},
		{
			name: '.find(fn)',
			desc: 'Return first matching element',
			example: '.find(x => x > 5)',
			color: '#c792ea'
		},
		{
			name: '.toArray()',
			desc: 'Collect all values into an array',
			example: '.toArray()',
			color: '#f78c6c'
		}
	];
</script>

<div class="slide slide-6">
	<div class="slide-heading">Iterator Helper <span class="accent">Methods</span></div>
	<div class="heading-bar"></div>

	<div class="methods-grid">
		{#each methods as m}
			<div class="method-card" style="--accent-color: {m.color}">
				<div class="method-name"><code>{m.name}</code></div>
				<div class="method-desc">{m.desc}</div>
				<div class="method-example"><code>{m.example}</code></div>
			</div>
		{/each}
	</div>
</div>

<style>
	.slide-6 {
		background: var(--dark);
	}

	.methods-grid {
		flex: 1;
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		grid-template-rows: repeat(4, 1fr);
		gap: 10px;
	}

	.method-card {
		background: rgba(255, 255, 255, 0.025);
		border: 1px solid rgba(255, 255, 255, 0.06);
		border-top: 2px solid var(--accent-color);
		border-radius: 10px;
		padding: 14px 14px 12px;
		display: flex;
		flex-direction: column;
		gap: 6px;
		transition:
			background 0.15s,
			border-color 0.15s;
	}

	.method-card:hover {
		background: rgba(255, 255, 255, 0.045);
	}

	.method-name code {
		font-size: var(--fsz-m);
		font-weight: 700;
		color: var(--accent-color);
		font-family: 'Fira Code', 'Cascadia Code', monospace;
	}

	.method-desc {
		font-size: var(--fsz-m);
		color: #b0b0c0;
		line-height: 1.45;
		flex: 1;
	}

	.method-example code {
		font-size: var(--fsz-m);
		color: #546e7a;
		font-family: 'Fira Code', 'Cascadia Code', monospace;
		background: rgba(255, 255, 255, 0.04);
		padding: 2px 6px;
		border-radius: 4px;
		display: block;
		white-space: nowrap;
		overflow: hidden;
		text-overflow: ellipsis;
	}
</style>
