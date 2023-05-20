<script lang="ts">
	import { T, useFrame } from '@threlte/core';
	import { interactivity, layers, OrbitControls } from '@threlte/extras';
	import { spring } from 'svelte/motion';
	import { Editable } from '@threlte/theatre';

	interactivity();
	const scale = spring(1);
	// let rotation = 0;
	// useFrame((state, delta) => (rotation += delta));
</script>


<!-- Change the color of scene -->
<!-- Camera -->
<T.PerspectiveCamera
	makeDefault
	position={[10, 10, 10]}
	on:create={({ ref }) => {
		ref.lookAt(0, 0, 0);
	}}
>
	<Editable name="Camera" transform />
	<OrbitControls enableDamping autoRotate />
</T.PerspectiveCamera>

<!-- Lights -->
<T.DirectionalLight position={[3, 10, 7]} intensity={1.5}>
	<Editable name="Directional Light" intensity position />
</T.DirectionalLight>
<T.AmbientLight intensity={0.5}>
	<Editable name="Ambient Light" intensity />
</T.AmbientLight>

<T.Mesh scale={$scale}>
	<Editable name="Box / Mesh" transform controls />
	<T.BoxGeometry args={[1, 5, 2]} />
	<T.MeshStandardMaterial color="green">
		<Editable name="Box / Material" color roughness metalness />
	</T.MeshStandardMaterial>
</T.Mesh>
