<script lang="ts">
	import { Canvas } from '@threlte/core';
	import { Theatre } from '@threlte/theatre';
	import { Studio } from '@threlte/theatre';

	import Scene from '$lib/components/Scene.svelte';
	import { dev } from '$app/environment';
</script>

<Studio enabled={dev} />
<Canvas>
	<Theatre>
		<Scene />
	</Theatre>
</Canvas>
