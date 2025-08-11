<script lang="ts">
	export let color: string = '#FFF';
	export let bgColor: string | undefined = '#F00';
	export let rounded: boolean = true;
</script>

<div
	class={`w-[30px] h-[30px] grid place-content-center overflow-hidden relative ${rounded && 'rounded-md'}`}
	style={`background-color:${bgColor}; color:${color}; --play-duration:1.1s;`}
>
	<div class="flex gap-0.5 items-center">
		<div
			class="w-1 h-1 rounded-full dot"
			style={`background-color:${color}; animation-delay: 0s;`}
		></div>
		<div
			class="w-1 h-1 rounded-full dot"
			style={`background-color:${color}; animation-delay: 0.10s;`}
		></div>
		<div
			class="w-1 h-1 rounded-full dot"
			style={`background-color:${color}; animation-delay: 0.20s;`}
		></div>
	</div>
</div>
