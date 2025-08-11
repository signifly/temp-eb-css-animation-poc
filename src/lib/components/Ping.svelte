<script lang="ts">
	export let pingColor: string = '#FF0000';
	export let bgColor: string | undefined = undefined;
	export let dotVariant: 'fill' | 'stroke' = 'fill';
	export let rounded: boolean = true;
	export let pingFilled: boolean = true;
</script>

<div
	class="h-[30px] w-[30px] relative {rounded
		? 'rounded-md'
		: 'rounded-full'} overflow-hidden grid place-content-center"
	style={bgColor ? `background-color:${bgColor};` : ''}
>
	{#if pingFilled}
		<div
			class="absolute left-1/2 top-1/2 h-[7.5px] w-[7.5px] -translate-x-1/2 -translate-y-1/2 rounded-full"
			style={`background-color:${pingColor};`}
		></div>
	{:else}
		<div
			class="absolute left-1/2 top-1/2 h-[7.5px] w-[7.5px] -translate-x-1/2 -translate-y-1/2 rounded-full border"
			style={`border-color:${pingColor};`}
		></div>
	{/if}

	<span
		style={`--target-size: 20px; --pause-size: 15px; border-color:${pingColor};`}
		class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 rounded-full [border-width:1px] [animation:ping-ripple-inner_1.1s_infinite] [animation-delay:0s]"
	></span>
	<span
		style={`--target-size: 30px; --pause-size: 22px; border-color:${pingColor};`}
		class="absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 rounded-full [border-width:1px] [animation:ping-ripple-outer_1.1s_infinite] [animation-delay:0.1s]"
	></span>
</div>
