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
		width="12"
		height="13"
		viewBox="0 0 12 13"
		fill="none"
		xmlns="http://www.w3.org/2000/svg"
		class="[animation:lens-flip_2.8s_linear_infinite]"
	>
		<path
			d="M10.7068 5.87745C11.1347 6.12446 11.1347 6.74196 10.7068 6.98897L1.08085 12.5465C0.65303 12.7935 0.118253 12.4848 0.118253 11.9908L0.118254 0.875644C0.118254 0.381638 0.65303 0.0728853 1.08085 0.319888L10.7068 5.87745Z"
			fill="#FF0000"
		/>
	</svg>
</div>
