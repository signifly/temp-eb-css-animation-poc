<script lang="ts">
	import Ping from '$lib/components/Ping.svelte';
	import Badge from '$lib/components/Badge.svelte';
	import Lens from '$lib/components/Lens.svelte';
	import Play from '$lib/components/Play.svelte';
	import Text from '$lib/components/Text.svelte';
	import Dots from '$lib/components/Dots.svelte';

	// Demo tool state
	let label = 'Breaking';
	let bgColor = '#000000';
	let textColor = '#FFFFFF';
	let rounded = true;
	let animated = true;

	type IconType = 'none' | 'ping' | 'lens' | 'play' | 'dots';
	let iconType: IconType = 'ping';

	// Icon-specific controls
	let pingColor = '#FF0000';
	let pingFilled = true;

	let iconFgColor = '#FF0000'; // for Lens/Play/Dots
	let iconBgColor = '#000000'; // for Lens/Play/Dots

	type TextAnim = 'none' | 'appear' | 'letters-up-stagger';
	let textAnimation: TextAnim = 'none';

	let iconComponent: any = undefined;
	let computedIconProps: any = undefined;

	$: iconComponent =
		iconType === 'ping'
			? Ping
			: iconType === 'lens'
				? Lens
				: iconType === 'play'
					? Play
					: iconType === 'dots'
						? Dots
						: undefined;

	$: {
		if (iconType === 'ping') {
			computedIconProps = { pingColor, pingFilled, bgColor };
		} else if (iconType === 'lens' || iconType === 'play' || iconType === 'dots') {
			computedIconProps = { color: iconFgColor, bgColor: iconBgColor };
		} else {
			computedIconProps = undefined;
		}
	}
</script>

<div class="w-screen grid place-content-center max-w-lg mx-auto px-4">
	<div
		class="place-content-center mt-12 flex flex-wrap gap-4 border border-gray-200 p-8 rounded-xl"
	>
		<Badge bgColor="#F00" icon={Ping} iconProps={{ pingColor: '#FFF', pingFilled: true }}>
			<Text animation="none" text="Lige nu" textColor="#FFF" />
		</Badge>

		<Ping pingColor="#F00" bgColor="black" pingFilled />

		<Lens bgColor="#F00" color="#FFF" rounded={false} />

		<Lens bgColor="#F00" color="#FFF" />

		<Play bgColor="#000" color="#F00" rounded={false} />

		<Play bgColor="#000" color="#F00" />

		<Ping pingColor="#F00" bgColor="#000" pingFilled={true} rounded={false} />

		<Badge bgColor="#F00" icon={Dots} iconProps={{ color: '#FFF' }}>
			<Text animation="letters-up-stagger" text="Opdateres" textColor="#FFF" />
		</Badge>

		<p>mangler</p>
		<p>mangler</p>

		<Ping pingColor="#F00" bgColor="#FF0" pingFilled={true} />

		<Badge
			bgColor="#000"
			icon={Ping}
			iconProps={{ pingColor: '#F00', pingFilled: true }}
			rounded={false}
		>
			<Text animation="none" textColor="#FFF" text="Breaking" />
		</Badge>

		<Badge
			bgColor="#000"
			icon={Ping}
			iconProps={{ pingColor: '#F00', pingFilled: true }}
			rounded={false}
			animated={false}
		>
			<Text animation="appear" textColor="#FFF" text="LIVE" />
		</Badge>

		<Badge bgColor="#FF0" icon={Ping} iconProps={{ pingColor: '#F00', pingFilled: true }}>
			<Text animation="none" textColor="#000" text="Breaking" />
		</Badge>

		<Ping pingColor="#FFF" bgColor="#F00" pingFilled={false} rounded={false} />

		<Ping pingColor="#F00" bgColor="#FF0" pingFilled={true} rounded={false} />

		<Ping pingColor="#FFF" bgColor="#F00" pingFilled={true} rounded={true} />

		<Badge
			bgColor="#000"
			icon={Play}
			rounded={false}
			iconProps={{ color: '#F00', bgColor: '#000' }}
		>
			<Text animation="none" textColor="#FFF" text="LIVE" />
		</Badge>

		<Badge
			bgColor="#F00"
			icon={Lens}
			animated={false}
			iconProps={{ color: '#FFF', bgColor: '#F00' }}
		>
			<Text animation="letters-up-stagger" textColor="#FFF" text="Afsløring" />
		</Badge>

		<Badge
			bgColor="#F00"
			icon={Lens}
			animated={false}
			rounded={false}
			iconProps={{ color: '#FFF', bgColor: '#F00' }}
		>
			<Text animation="letters-up-stagger" textColor="#FFF" text="Afsløring" />
		</Badge>

		<Badge
			bgColor="#F00"
			icon={Ping}
			rounded={false}
			iconProps={{ pingColor: '#FFF', bgColor: '#F00' }}
		>
			<Text animation="none" textColor="#FFF" text="Lige nu" />
		</Badge>

		<Badge bgColor="#F00" rounded={false}>
			<Text animation="none" textColor="#FFF" text="Opdateres" />
		</Badge>

		<Badge
			bgColor="#000"
			icon={Ping}
			rounded={true}
			iconProps={{ pingColor: '#F00', pingFilled: true }}
		>
			<Text animation="none" textColor="#FFF" text="Breaking" />
		</Badge>

		<Badge
			bgColor="#FF0"
			icon={Ping}
			rounded={false}
			iconProps={{ pingColor: '#F00', pingFilled: true }}
		>
			<Text animation="none" textColor="#000" text="Breaking" />
		</Badge>

		<Dots color="#FFF" bgColor="#F00" />

		<Dots color="#FFF" bgColor="#F00" rounded={false} />
	</div>

	<!-- Customizer -->
	<section class="mt-8 w-full mb-12">
		<h2 class="text-base md:text-lg font-semibold mb-3">Customize your badge</h2>
		<div class="grid md:grid-cols-2 gap-6">
			<!-- Controls -->
			<div class="space-y-4">
				<div class="grid grid-cols-2 gap-3 items-center">
					<label class="text-sm text-gray-700" for="label">Label</label>
					<input id="label" class="border rounded px-2 py-1" type="text" bind:value={label} />
					<label class="text-sm text-gray-700" for="bgColor">Background</label>
					<input id="bgColor" class="h-8 w-14" type="color" bind:value={bgColor} />
					<label class="text-sm text-gray-700" for="textColor">Text color</label>
					<input id="textColor" class="h-8 w-14" type="color" bind:value={textColor} />
					<label class="text-sm text-gray-700" for="rounded">Rounded</label>
					<input id="rounded" type="checkbox" class="h-4 w-4" bind:checked={rounded} />
					<label class="text-sm text-gray-700" for="animated">background animation</label>
					<input id="animated" type="checkbox" class="h-4 w-4" bind:checked={animated} />
					<label class="text-sm text-gray-700" for="textAnimation">Text animation</label>
					<select id="textAnimation" class="border rounded px-2 py-1" bind:value={textAnimation}>
						<option value="none">None</option>
						<option value="appear">Appear</option>
						<option value="letters-up-stagger">Letters up stagger</option>
					</select>
					<label class="text-sm text-gray-700" for="iconType">Icon</label>
					<select id="iconType" class="border rounded px-2 py-1" bind:value={iconType}>
						<option value="none">None</option>
						<option value="ping">Ping</option>
						<option value="lens">Lens</option>
						<option value="play">Play</option>
						<option value="dots">Dots</option>
					</select>
				</div>

				{#if iconType === 'ping'}
					<div class="grid grid-cols-2 gap-3 items-center">
						<label class="text-sm text-gray-700" for="pingColor">Ping color</label>
						<input id="pingColor" class="h-8 w-14" type="color" bind:value={pingColor} />
						<label class="text-sm text-gray-700" for="pingFilled">Ping filled</label>
						<input id="pingFilled" type="checkbox" class="h-4 w-4" bind:checked={pingFilled} />
					</div>
				{:else if iconType === 'lens' || iconType === 'play' || iconType === 'dots'}
					<div class="grid grid-cols-2 gap-3 items-center">
						<label class="text-sm text-gray-700" for="iconFgColor">Icon color</label>
						<input id="iconFgColor" class="h-8 w-14" type="color" bind:value={iconFgColor} />
						<label class="text-sm text-gray-700" for="iconBgColor">Icon background</label>
						<input id="iconBgColor" class="h-8 w-14" type="color" bind:value={iconBgColor} />
					</div>
				{/if}
			</div>

			<!-- Preview -->
			<div class="flex items-center justify-center border border-gray-200 rounded-lg p-6 min-h-28">
				<Badge {bgColor} icon={iconComponent} iconProps={computedIconProps} {rounded} {animated}>
					<Text animation={textAnimation} {textColor} text={label} />
				</Badge>
			</div>
		</div>
	</section>
</div>
