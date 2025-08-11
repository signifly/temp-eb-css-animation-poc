<script lang="ts">
	import Ping from '$lib/components/Ping.svelte';

	export let pingColor: string = '#FFFFFF';
	export let pingFilled: boolean = false;
	export let bgColor: string = '#FF0000';
	export let rounded: boolean = true;
</script>

<div
	class="flex items-center w-fit {rounded
		? 'rounded-md'
		: 'rounded-none'} overflow-hidden relative pr-2 gap-1"
>
	<div class="z-10 relative">
		<Ping {pingColor} {pingFilled} />
	</div>

	<slot />

	<div
		class="absolute inset-y-0 left-0 right-0 [animation:badge-fill-sweep-x_8.8s_linear_infinite] z-0"
		style={`background-color:${bgColor};`}
	></div>
</div>
