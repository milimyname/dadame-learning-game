<!--
Auto-generated by: https://github.com/threlte/threlte/tree/main/packages/gltf
Command: npx @threlte/gltf@1.0.0-next.12 ./park.glb -t
-->

<script lang="ts">
	import type * as THREE from 'three';
	import { Group } from 'three';
	import { T, type Props, type Events, type Slots, forwardEventHandlers } from '@threlte/core';
	import { interactivity, useGltf, useGltfAnimations } from '@threlte/extras';
	import { spring } from 'svelte/motion';

	type $$Props = Props<THREE.Group>;
	type $$Events = Events<THREE.Group>;
	type $$Slots = Slots<THREE.Group> & { fallback: {}; error: { error: any } };
	let scale = spring(1);
	interactivity();

	export const ref = new Group();

	type ActionName =
		| 'Cube'
		| 'Plane.002'
		| 'Plane.003'
		| 'Plane.004'
		| 'Plane.005'
		| 'Plane.006'
		| 'Plane.007'
		| 'Plane.008'
		| 'Plane.009'
		| 'Plane.010'
		| 'Cylinder.001'
		| 'Plane.011'
		| 'Icosphere.003'
		| 'Icosphere.004'
		| 'Icosphere.005'
		| 'Icosphere.006'
		| 'Icosphere.007'
		| 'Plane.001'
		| 'Cylinder'
		| 'Cube.019'
		| 'Icosphere'
		| 'Icosphere.001'
		| 'Icosphere.002'
		| 'Cube.020';
	type GLTFResult = {
		nodes: {
			Cube: THREE.Mesh;
			Plane002: THREE.Mesh;
			Plane003: THREE.Mesh;
			Plane004: THREE.Mesh;
			Plane005: THREE.Mesh;
			Plane006: THREE.Mesh;
			Plane007: THREE.Mesh;
			Plane008: THREE.Mesh;
			Plane009: THREE.Mesh;
			Plane010: THREE.Mesh;
			Cylinder001: THREE.Mesh;
			Plane011: THREE.Mesh;
			Icosphere003: THREE.Mesh;
			Icosphere004: THREE.Mesh;
			Icosphere005: THREE.Mesh;
			Icosphere006: THREE.Mesh;
			Icosphere007: THREE.Mesh;
			Plane001: THREE.Mesh;
			Cylinder_1: THREE.Mesh;
			Cylinder_2: THREE.Mesh;
			Cube019: THREE.Mesh;
			Icosphere: THREE.Mesh;
			Icosphere001: THREE.Mesh;
			Icosphere002: THREE.Mesh;
			Cube020: THREE.Mesh;
		};
		materials: {
			Material: THREE.MeshStandardMaterial;
			['Material.001']: THREE.MeshStandardMaterial;
			['NoSign.004']: THREE.MeshStandardMaterial;
			['Material.003']: THREE.MeshStandardMaterial;
			['Material.002']: THREE.MeshStandardMaterial;
		};
	};

	const gltf = useGltf<GLTFResult>('/park.glb');
	export const { actions, mixer } = useGltfAnimations<ActionName>(gltf, ref);

	const component = forwardEventHandlers();
</script>

<T is={ref} dispose={false} {...$$restProps} bind:this={$component}>
	{#await gltf}
		<slot name="fallback" />
	{:then gltf}
		<T.Group name="Scene">
			<T.Mesh name="Cube" geometry={gltf.nodes.Cube.geometry} material={gltf.materials.Material} />
			<T.Mesh
				name="Plane002"
				geometry={gltf.nodes.Plane002.geometry}
				material={gltf.materials['Material.001']}
				position={[-3.29, 5.7, 7.1]}
				rotation={[0.77, -0.56, 1.12]}
				scale={0.26}
			/>
			<T.Mesh
				name="Plane003"
				geometry={gltf.nodes.Plane003.geometry}
				material={gltf.materials['Material.001']}
				position={[-3.61, 4.78, 6.55]}
				rotation={[-0.18, -0.06, -0.09]}
				scale={0.26}
			/>
			<T.Mesh
				name="Plane004"
				geometry={gltf.nodes.Plane004.geometry}
				material={gltf.materials['Material.001']}
				position={[-4.43, 5.07, 7.15]}
				rotation={[-0.18, -0.06, -0.09]}
				scale={0.26}
			/>
			<T.Mesh
				name="Plane005"
				geometry={gltf.nodes.Plane005.geometry}
				material={gltf.materials['Material.001']}
				position={[-4.9, 4.44, 6.88]}
				rotation={[0.88, -0.54, 1.26]}
				scale={0.26}
			/>
			<T.Mesh
				name="Plane006"
				geometry={gltf.nodes.Plane006.geometry}
				material={gltf.materials['Material.001']}
				position={[-3.93, 6.09, 7.38]}
				rotation={[-0.3, -0.28, -0.44]}
				scale={0.3}
			/>
			<T.Mesh
				name="Plane007"
				geometry={gltf.nodes.Plane007.geometry}
				material={gltf.materials['Material.001']}
				position={[-6.66, 3.55, 6.95]}
				rotation={[-0.18, -0.06, -0.09]}
				scale={0.21}
			/>
			<T.Mesh
				name="Plane008"
				geometry={gltf.nodes.Plane008.geometry}
				material={gltf.materials['Material.001']}
				position={[-7.24, 2.81, 6.76]}
				rotation={[0.34, -0.44, 1.02]}
				scale={0.21}
			/>
			<T.Mesh
				name="Plane009"
				geometry={gltf.nodes.Plane009.geometry}
				material={gltf.materials['Material.001']}
				position={[-7.52, 3.22, 6.97]}
				rotation={[-0.06, -0.24, 0.25]}
				scale={0.21}
			/>
			<T.Mesh
				name="Plane010"
				geometry={gltf.nodes.Plane010.geometry}
				material={gltf.materials['Material.001']}
				position={[-4.08, 3.85, 6.89]}
				rotation={[-1.71, -0.17, -0.75]}
				scale={0.26}
			/>
			<T.Mesh
				name="Cylinder001"
				geometry={gltf.nodes.Cylinder001.geometry}
				material={gltf.materials.Material}
				position={[-4.65, 1.35, 4.67]}
				scale={0.75}
			/>
			<T.Mesh
				name="Plane011"
				geometry={gltf.nodes.Plane011.geometry}
				material={gltf.materials['NoSign.004']}
				position={[-4.65, 2.03, 4.56]}
				rotation={[Math.PI / 2, 0, 0]}
				scale={[0.46, 0.78, 0.46]}
			/>
			<T.Mesh
				name="Icosphere003"
				geometry={gltf.nodes.Icosphere003.geometry}
				material={gltf.materials['Material.001']}
				position={[0, -1.31, 2.75]}
				scale={[8.82, 2.01, 8.82]}
			/>
			<T.Mesh
				name="Icosphere004"
				geometry={gltf.nodes.Icosphere004.geometry}
				material={gltf.materials.Material}
				position={[0, -2.35, 2.75]}
				rotation={[0, 0.18, -0.06]}
				scale={[6.93, 2.64, 6.93]}
			/>
			<T.Mesh
				name="Icosphere005"
				geometry={gltf.nodes.Icosphere005.geometry}
				material={gltf.materials.Material}
				position={[-1.47, -5.71, -1.58]}
				scale={2.22}
			/>
			<T.Mesh
				name="Icosphere006"
				geometry={gltf.nodes.Icosphere006.geometry}
				material={gltf.materials.Material}
				position={[0.58, -4.69, 5.29]}
				rotation={[2.48, -0.22, -0.42]}
				scale={2.22}
			/>
			<T.Mesh
				name="Icosphere007"
				geometry={gltf.nodes.Icosphere007.geometry}
				material={gltf.materials.Material}
				position={[3.61, -4.59, 0.67]}
				rotation={[2.48, -0.22, -0.42]}
				on:pointerenter={() => {
					scale.set(2.22);
				}}
				on:pointerleave={() => {
					scale.set(1);
				}}
				scale={$scale}
			/>
			<T.Mesh
				name="Plane001"
				geometry={gltf.nodes.Plane001.geometry}
				material={gltf.materials['Material.003']}
			/>
			<T.Group name="Cylinder" position={[0.63, -1.03, -3.36]} scale={[3.25, 1.47, 3.25]}>
				<T.Mesh
					name="Cylinder_1"
					geometry={gltf.nodes.Cylinder_1.geometry}
					material={gltf.materials['Material.003']}
				/>
				<T.Mesh
					name="Cylinder_2"
					geometry={gltf.nodes.Cylinder_2.geometry}
					material={gltf.materials['Material.002']}
				/>
			</T.Group>
			<T.Mesh
				name="Cube019"
				geometry={gltf.nodes.Cube019.geometry}
				material={gltf.materials.Material}
			/>
			<T.Mesh
				name="Icosphere"
				geometry={gltf.nodes.Icosphere.geometry}
				material={gltf.materials['Material.001']}
				position={[-1.18, 6.02, 7.4]}
				scale={0.99}
			/>
			<T.Mesh
				name="Icosphere001"
				geometry={gltf.nodes.Icosphere001.geometry}
				material={gltf.materials['Material.001']}
				position={[1.36, 5.49, 6.24]}
				scale={1.12}
			/>
			<T.Mesh
				name="Icosphere002"
				geometry={gltf.nodes.Icosphere002.geometry}
				material={gltf.materials['Material.001']}
				position={[0.63, 6.54, 7.37]}
				scale={1.5}
			/>
			<T.Mesh
				name="Cube020"
				geometry={gltf.nodes.Cube020.geometry}
				material={gltf.materials['Material.003']}
				position={[-4.53, 0.19, -2.15]}
				scale={0.84}
			/>
		</T.Group>
	{:catch error}
		<slot name="error" {error} />
	{/await}

	<slot {ref} />
</T>
