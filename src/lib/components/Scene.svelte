<script lang="ts">
	import { T, useFrame } from '@threlte/core';
	import { interactivity, OrbitControls } from '@threlte/extras';
	import { spring } from 'svelte/motion';

	interactivity();
	const scale = spring(1);
	// let rotation = 0;
	// useFrame((state, delta) => (rotation += delta));
</script>

<!-- Camera -->
<T.PerspectiveCamera
	makeDefault
	position={[10, 10, 10]}
	on:create={({ ref }) => {
		ref.lookAt(0, 0, 0);
	}}
>
	<OrbitControls enableDamping autoRotate />
</T.PerspectiveCamera>

<!-- Lights -->
<T.DirectionalLight position={[3, 10, 7]} intensity={1.5} />

<T.Mesh scale={$scale} on:pointerenter={() => scale.set(1.5)} on:pointerleave={() => scale.set(1)}>
	<T.BoxGeometry args={[1, 5, 2]} />
	<T.MeshStandardMaterial color="green" />
</T.Mesh>
