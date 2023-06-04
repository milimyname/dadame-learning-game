<script lang="ts">
	import { T } from '@threlte/core';
	import { interactivity, OrbitControls, Environment, GLTF } from '@threlte/extras';
	import { spring } from 'svelte/motion';
	import { Editable } from '@threlte/theatre';
	import Portal from '$lib/components/Portal.svelte';
	import Park from '$lib/components/Park.svelte';

	interactivity();
	const scale = spring(1);
</script>

<!-- Camera -->
<T.PerspectiveCamera
	makeDefault
	position={[10, 10, 10]}
	on:create={({ ref }) => {
		ref.lookAt(0, 0, 0);
	}}
>
	<Editable name="Camera" transform />
	<OrbitControls enableDamping autoRotate maxPolarAngle={Math.PI / 2}>
		<Editable name="Orbit Controls" transform maxPolarAngle />
	</OrbitControls>
</T.PerspectiveCamera>

<!-- Lights -->
<!-- <T.DirectionalLight position={[3, 10, 7]} intensity={1.5}>
	<Editable name="Directional Light" intensity position />
</T.DirectionalLight> -->
<T.AmbientLight intensity={1}>
	<Editable name="Ambient Light" intensity />
</T.AmbientLight>
<!-- <Environment files={'./light.hdr'} /> -->

<Park />
<!-- <Portal /> -->

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
