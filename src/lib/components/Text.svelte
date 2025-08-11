<script lang="ts">
	export let animation: 'appear' | 'letters-up-stagger' | 'none' = 'none';
	export let text: string = '';
	export let textColor: string = '#000';

	let chars: string[] = [];
	$: chars = Array.from(text ?? '');

	const TOTAL = 1; // seconds

	const STAGGER = 0.9;
	const APPEAR = 0.9;

	const getItemDelay = () => {
		if (animation === 'appear') return APPEAR;

		return STAGGER;
	};

	const ITEM_DELAY = getItemDelay();

	const delayFor = (i: number, n: number) =>
		n > 1 ? (i / (n - 1)) * Math.max(TOTAL - ITEM_DELAY, 0) : 0;
</script>

<p class="uppercase text-xl leading-none pt-0.5 z-10" style={`color:${textColor};`}>
	{#each chars as char, i}
		<span
			class={`inline-block 
            ${animation === 'appear' && '[animation:text-appear_0.1s_both]'} 
            ${animation === 'letters-up-stagger' && '[animation:text-letters-up-stagger_0.4s_both]'}
            ${animation === 'none' && 'opacity-100'}`}
			style:animation-delay={delayFor(i, chars.length) + 's'}
		>
			{char}
		</span>
	{/each}
</p>
