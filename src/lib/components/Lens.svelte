<script lang="ts">
	export let color: string = '#FFF';
	export let bgColor: string | undefined = '#F00';
	export let rounded: boolean = true;
</script>

<div
	class={`w-[30px] h-[30px] grid place-content-center bg-red-500 ${rounded && 'rounded-md'}`}
	style={`background-color:${bgColor}; color:${color};`}
>
	<svg
		width="16"
		height="16"
		viewBox="0 0 21 20"
		fill="none"
		xmlns="http://www.w3.org/2000/svg"
		class="[animation:lens-flip_2.8s_linear_infinite]"
	>
		<path d="M6.53547 1.09473H1.40161V6.22858" stroke="white" stroke-width="1.28346" />
		<path
			d="M1.40161 13.9291L1.40161 19.063L6.53547 19.063"
			stroke="white"
			stroke-width="1.28346"
		/>
		<path
			d="M14.2363 19.063L19.3701 19.063L19.3701 13.9291"
			stroke="white"
			stroke-width="1.28346"
		/>
		<path
			d="M19.3701 6.22858L19.3701 1.09473L14.2363 1.09473"
			stroke="white"
			stroke-width="1.28346"
		/>
		<circle cx="10.3858" cy="10.0789" r="3.85039" fill="white" />
	</svg>
</div>
