<script lang="ts">
	import Ping from '$lib/components/Ping.svelte';
	import Badge from '$lib/components/Badge.svelte';
	import Lens from '$lib/components/Lens.svelte';
	import Play from '$lib/components/Play.svelte';
</script>

<div class="w-screen h-screen grid place-content-center">
	<div class="grid place-content-center grid-cols-3 gap-4 border border-gray-200 p-8 rounded-xl">
		<Ping pingColor="#F00" bgColor="black" pingFilled />

		<Ping pingColor="#FFF" bgColor="#F00" pingFilled={false} />

		<Ping pingColor="#00F" bgColor="#FFF" pingFilled={true} />

		<Badge pingColor="#FFF" textColor="#FFF" bgColor="#F00" text="Lige nu" />

		<Badge pingColor="#F00" textColor="#000" bgColor="#FF0" text="Breaking" pingFilled />

		<Badge
			pingColor="#F00"
			textColor="#FFF"
			bgColor="#000"
			text="Breaking"
			pingFilled
			rounded={false}
		/>

		<Lens color="#FFF" bgColor="#F00" />
		<Lens color="#FFF" bgColor="#F00" rounded={false} />
		<Play color="#F00" bgColor="#000" />
		<Play color="#F00" bgColor="#000" rounded={false} />
	</div>
</div>
