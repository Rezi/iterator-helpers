<script lang="ts">
	import '../app.css';
	import { goto } from '$app/navigation';
	import { page } from '$app/state';

	let { children } = $props();

	const TOTAL = 10;
	const current = $derived(parseInt((page.params as { slide?: string }).slide ?? '0'));

	function prev() {
		if (current > 1) goto(`/${current - 1}`);
	}
	function next() {
		if (current < TOTAL) goto(`/${current + 1}`);
	}

	function onKeydown(e: KeyboardEvent) {
		if (e.key === 'ArrowRight' || e.key === 'ArrowDown') next();
		else if (e.key === 'ArrowLeft' || e.key === 'ArrowUp') prev();
	}
</script>

<svelte:window onkeydown={onKeydown} />

{@render children()}

{#if current > 0}
	<nav class="slide-nav">
		<button onclick={prev} disabled={current <= 1} class="nav-btn" title="Previous (←)">←</button>
		<span class="slide-count">{current} / {TOTAL}</span>
		<button onclick={next} disabled={current >= TOTAL} class="nav-btn" title="Next (→)">→</button>
	</nav>
{/if}

<style>
	.slide-nav {
		position: fixed;
		bottom: 22px;
		left: 50%;
		transform: translateX(-50%);
		display: flex;
		align-items: center;
		gap: 14px;
		background: rgba(28, 28, 46, 0.85);
		border: 1px solid rgba(255, 255, 255, 0.08);
		backdrop-filter: blur(10px);
		border-radius: 40px;
		padding: 7px 18px;
		z-index: 100;
	}

	.nav-btn {
		background: none;
		border: none;
		color: var(--light, #f0f0f0);
		font-size: 1.1rem;
		cursor: pointer;
		padding: 4px 10px;
		border-radius: 6px;
		transition:
			background 0.15s,
			color 0.15s,
			opacity 0.15s;
		opacity: 0.75;
	}

	.nav-btn:hover:not(:disabled) {
		background: rgba(250, 198, 31, 0.15);
		color: #fac61f;
		opacity: 1;
	}

	.nav-btn:disabled {
		opacity: 0.2;
		cursor: default;
	}

	.slide-count {
		font-size: 0.8rem;
		color: #848484;
		min-width: 44px;
		text-align: center;
		font-variant-numeric: tabular-nums;
	}
</style>
