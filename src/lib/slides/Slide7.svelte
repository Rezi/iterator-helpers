<script lang="ts">
	const rows = [
		{
			dim: 'Evaluation',
			arrayVal: 'Eager — runs immediately',
			iterVal: 'Lazy — runs on demand',
			arrayBad: true
		},
		{
			dim: 'Intermediate arrays',
			arrayVal: 'Created at every step',
			iterVal: 'None — elements flow through',
			arrayBad: true
		},
		{
			dim: 'Early termination',
			arrayVal: 'No — always processes all',
			iterVal: 'Yes — stop anytime',
			arrayBad: true
		},
		{
			dim: 'Infinite sequences',
			arrayVal: 'Not possible',
			iterVal: 'Native support',
			arrayBad: true
		},
		{
			dim: 'Memory usage',
			arrayVal: 'Proportional to array size',
			iterVal: 'Constant (O(1))',
			arrayBad: true
		},
		{
			dim: 'Random access',
			arrayVal: 'Yes — arr[i] any time',
			iterVal: 'No — forward only',
			arrayBad: false
		},
		{
			dim: 'Re-usability',
			arrayVal: 'Can be iterated many times',
			iterVal: 'Single-pass only',
			arrayBad: false
		},
		{
			dim: 'Browser support',
			arrayVal: 'Universal',
			iterVal: 'Node 22+ / modern browsers',
			arrayBad: false
		}
	];
</script>

<div class="slide slide-7">
	<div class="slide-heading">Array Methods <span class="accent">vs</span> Iterator Helpers</div>
	<div class="heading-bar"></div>

	<div class="body">
		<div class="comparison-table">
			<!-- Header -->
			<div class="col-header left-header">
				<span class="header-icon">📋</span>
				<span>Array Methods</span>
			</div>
			<div class="col-header center-header">Dimension</div>
			<div class="col-header right-header">
				<span class="header-icon">⚡</span>
				<span>Iterator Helpers</span>
			</div>

			{#each rows as row}
				<div class="cell left-cell" class:cell-bad={row.arrayBad}>
					{row.arrayVal}
					{#if row.arrayBad}
						<span class="cell-icon bad">✗</span>
					{:else}
						<span class="cell-icon ok">✓</span>
					{/if}
				</div>
				<div class="cell dim-cell">{row.dim}</div>
				<div class="cell right-cell" class:cell-good={!row.arrayBad}>
					{#if !row.arrayBad}
						<span class="cell-icon ok">✓</span>
					{:else}
						<span class="cell-icon ok">✓</span>
					{/if}
					{row.iterVal}
				</div>
			{/each}
		</div>

		<div class="takeaway">
			<span class="takeaway-icon">💡</span>
			<p>
				Iterator helpers don't replace arrays — they <strong>extend</strong> how you work with sequences.
				Use them when laziness, memory, or early termination matter.
			</p>
		</div>
	</div>
</div>

<style>
	.slide-7 {
		background: var(--dark);
	}

	.body {
		flex: 1;
		display: flex;
		flex-direction: column;
		gap: 20px;
	}

	.comparison-table {
		display: grid;
		grid-template-columns: 1fr 180px 1fr;
		gap: 0;
		border-radius: 12px;
		overflow: hidden;
		border: 1px solid rgba(255, 255, 255, 0.07);
		flex: 1;
	}

	.col-header {
		padding: 12px 20px;
		font-size: var(--fsz-s);
		font-weight: 700;
		letter-spacing: 0.07em;
		text-transform: uppercase;
		display: flex;
		align-items: center;
		gap: 8px;
	}

	.left-header {
		background: rgba(255, 107, 107, 0.08);
		color: #ff9090;
		border-bottom: 1px solid rgba(255, 107, 107, 0.15);
	}

	.center-header {
		background: rgba(255, 255, 255, 0.03);
		color: var(--gray);
		text-align: center;
		justify-content: center;
		border-bottom: 1px solid rgba(255, 255, 255, 0.06);
		border-left: 1px solid rgba(255, 255, 255, 0.06);
		border-right: 1px solid rgba(255, 255, 255, 0.06);
	}

	.right-header {
		background: rgba(250, 198, 31, 0.08);
		color: var(--yellow);
		border-bottom: 1px solid rgba(250, 198, 31, 0.15);
	}

	.header-icon {
		font-size: var(--fsz-m);
	}

	.cell {
		padding: 9px 20px;
		font-size: var(--fsz-s);
		display: flex;
		align-items: center;
		gap: 8px;
		color: #c0c0d0;
		border-bottom: 1px solid rgba(255, 255, 255, 0.04);
	}

	.cell:last-child,
	.cell:nth-last-child(2),
	.cell:nth-last-child(3) {
		border-bottom: none;
	}

	.left-cell {
		background: rgba(255, 107, 107, 0.03);
		justify-content: flex-end;
	}

	.left-cell.cell-bad {
		color: #c0a0a0;
	}

	.dim-cell {
		background: rgba(255, 255, 255, 0.02);
		color: var(--gray);
		font-size: var(--fsz-s);
		font-weight: 600;
		text-transform: uppercase;
		letter-spacing: 0.06em;
		justify-content: center;
		text-align: center;
		border-left: 1px solid rgba(255, 255, 255, 0.04);
		border-right: 1px solid rgba(255, 255, 255, 0.04);
	}

	.right-cell {
		background: rgba(250, 198, 31, 0.03);
	}

	.right-cell.cell-good {
		color: #c0d0b0;
	}

	.cell-icon {
		font-size: var(--fsz-s);
		flex-shrink: 0;
	}

	.cell-icon.bad {
		color: #ff6b6b;
		opacity: 0.7;
	}

	.cell-icon.ok {
		color: var(--green);
		opacity: 0.8;
	}

	.takeaway {
		display: flex;
		align-items: flex-start;
		gap: 14px;
		background: rgba(250, 198, 31, 0.06);
		border: 1px solid rgba(250, 198, 31, 0.2);
		border-radius: 10px;
		padding: 14px 18px;
	}

	.takeaway-icon {
		font-size: var(--fsz-m);
		flex-shrink: 0;
	}

	.takeaway p {
		font-size: var(--fsz-s);
		color: #b0b0c0;
		line-height: 1.6;
	}

	.takeaway strong {
		color: var(--yellow);
	}
</style>
