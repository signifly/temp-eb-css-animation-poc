<script lang="ts">
	import Ping from '$lib/components/Ping.svelte';
	import Lens from '$lib/components/Lens.svelte';
	import Play from '$lib/components/Play.svelte';
	import Dots from '$lib/components/Dots.svelte';

	export let pingColor: string = '#FFFFFF';
	export let pingFilled: boolean = false;
	export let bgColor: string = '#FF0000';
	export let rounded: boolean = true;
	export let animated: boolean = true;

	// New: allow passing a component to render as the leading icon/animation
	export let icon: typeof Ping | typeof Lens | typeof Play | typeof Dots = Ping;
	// New: props to forward to the chosen icon component
	export let iconProps: Record<string, unknown> = {};
</script>

<div
	class="flex items-center w-fit {rounded
		? 'rounded-md'
		: 'rounded-none'} overflow-hidden relative pr-2 gap-1"
>
	<div class="z-10 relative">
		<svelte:component this={icon} {...iconProps} {rounded} />
	</div>

	<slot />

	<div
		class={`absolute inset-y-0 left-0 right-0 ${
			animated ? '[animation:badge-fill-sweep-x_8.8s_linear_infinite]' : ''
		} z-0`}
		style={`background-color:${bgColor};`}
	></div>
</div>
