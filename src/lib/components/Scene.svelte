<script lang="ts">
	import { T, useFrame } from '@threlte/core';
	import { interactivity, OrbitControls, Environment } from '@threlte/extras';
	import { Editable } from '@threlte/theatre';
	import Tiktak from './Tiktak.svelte';

	interactivity();
	let innerWidth = 0;

	// Keep the camera look at the center of the scene
	// useFrame(({ camera }) => {
	// 	camera.current.lookAt(0, 0, 0);
	// });
</script>

<svelte:window {innerWidth} />

<!-- Camera -->
<T.PerspectiveCamera
	makeDefault
	position={[10, innerWidth > 450 ? 10 : 40, 10]}
	on:create={({ ref }) => {
		ref.lookAt(0, 0, 0);
	}}
>
	<Editable name="Camera" transform />
	<OrbitControls
		enableDamping
		maxPolarAngle={Math.PI / 5}
		enablePan={false}
		maxDistance={innerWidth > 450 ? 25 : 40}
		minDistance{innerWidt
	>
		450 ? 20 : 40}>
		<Editable name="Orbit Controls" transform maxPolarAngle maxDistance minDistance />
	</OrbitControls>
</T.PerspectiveCamera>

<!-- Lights -->
<!-- <T.DirectionalLight position={[3, 10, 7]} intensity={1}>
	<Editable name="Directional Light" intensity position />
</T.DirectionalLight> -->
<T.AmbientLight intensity={1}>
	<Editable name="Ambient Light" intensity />
</T.AmbientLight>
<Environment files={'./light.hdr'} isBackground />

<Tiktak />
<!-- <GLTF url="src/lib/assets/model.gltf">
	<Editable name="Model" transform controls castShadow receiveShadow />
</GLTF> -->
<!-- <GLTF url="src/lib/assets/molang_3_d_copy.gltf" /> -->

<!-- <T.Mesh scale={$scale}>
	<Editable name="Box / Mesh" transform controls castShadow />
	<T.BoxGeometry args={[1, 5, 2]} />
	<T.MeshStandardMaterial color="green">
		<Editable name="Box / Material" color roughness metalness />
	</T.MeshStandardMaterial>
</T.Mesh>

<T.Mesh scale={$scale} rotation.x={90} position={[3, -2.55, 0]}>
	<Editable name="Circle / Mesh" transform controls receiveShadow />
	<T.CircleGeometry args={[10]} />
	<T.MeshBasicMaterial color="white" side={DoubleSide}>
		<Editable name="Circle / Material" color roughness metalness />
	</T.MeshBasicMaterial>
</T.Mesh> -->
