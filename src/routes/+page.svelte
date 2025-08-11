<script lang="ts">
	import Ping from '$lib/components/Ping.svelte';
	import Badge from '$lib/components/Badge.svelte';
	import Lens from '$lib/components/Lens.svelte';
	import Play from '$lib/components/Play.svelte';
	import Text from '$lib/components/Text.svelte';
</script>

<div class="w-screen h-screen grid place-content-center">
	<div class="grid place-content-center grid-cols-3 gap-4 border border-gray-200 p-8 rounded-xl">
		<Ping pingColor="#F00" bgColor="black" pingFilled />

		<Ping pingColor="#FFF" bgColor="#F00" pingFilled={false} />

		<Ping pingColor="#00F" bgColor="#FFF" pingFilled={true} />

		<Badge pingColor="#FFF" bgColor="#F00">
			<Text animation="appear" text="Lige nu" textColor="#FFF" />
		</Badge>

		<Badge pingColor="#F00" bgColor="#FF0" pingFilled>
			<Text animation="appear" text="Breaking" textColor="#000" />
		</Badge>

		<Badge pingColor="#F00" bgColor="#000" pingFilled rounded={false}>
			<Text animation="appear" text="Breaking" textColor="#FFF" />
		</Badge>

		<Badge pingColor="#F00" bgColor="#000" pingFilled>
			<Text animation="letters-up-stagger" text="Opdateres" textColor="#FFF" />
		</Badge>

		<Badge pingColor="#FFF" bgColor="#F00" pingFilled rounded={false}>
			<Text animation="letters-up-stagger" text="Opdateres" textColor="#FFF" />
		</Badge>

		<Lens color="#FFF" bgColor="#F00" />
		<Lens color="#FFF" bgColor="#F00" rounded={false} />
		<Play color="#F00" bgColor="#000" />
		<Play color="#F00" bgColor="#000" rounded={false} />
	</div>
</div>
