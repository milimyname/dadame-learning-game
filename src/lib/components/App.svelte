<script lang="ts">
	import { Canvas } from '@threlte/core';
	import { Theatre } from '@threlte/theatre';
	import { Studio } from '@threlte/theatre';

	import Scene from './Scene.svelte';
</script>

<Studio enabled={import.meta.env.DEV} />
<Canvas>
	<Theatre>
		<Scene />
	</Theatre>
</Canvas>
