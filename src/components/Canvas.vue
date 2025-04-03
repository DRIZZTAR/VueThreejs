<script lang="ts" setup>
import { TresCanvas } from '@tresjs/core';
import {
	OrbitControls,
	Levioso,
	Environment,
	Tetrahedron,
	Precipitation,
	Text3D,
	Ocean,
} from '@tresjs/cientos';
</script>

<template>
	<TresCanvas window-size preset="realistic">
		<Suspense>
			<Environment :background="true" :blur="0.2" preset="sunset" />
		</Suspense>
		<TresPerspectiveCamera :position="[0, 5, 10]" />
		<OrbitControls />
		<TresAmbientLight :intensity="2.0" />
		<Precipitation :randomness="0" :speed="1" :count="2500" />
		<Suspense>
			<Levioso>
				<Text3D
					text="VUE"
					:size="3.0"
					font="/italic.json"
					:position="[0, 1.4, 0]"
				>
					<TresMeshStandardMaterial
						:color="0x00ff00"
						:metalness="1.5"
						:roughness="0.0"
					/>
				</Text3D>
			</Levioso>
		</Suspense>
		<Suspense>
			<Ocean>
				<TresCircleGeometry :args="[50, 16]" />
			</Ocean>
		</Suspense>
		<Levioso
			:speed="3"
			:range="[2, 3.0]"
			:rotationFactor="5.0"
		>
			<Tetrahedron :args="[1, 0]" :position="[0, 1.3, 0]">
				<TresMeshStandardMaterial
					:color="0x00ff00"
					:metalness="1.5"
					:roughness="0.0"
				/>
			</Tetrahedron>
		</Levioso>
	</TresCanvas>
</template>

<style>
html,
body {
	margin: 0;
	padding: 0;
	height: 100%;
	width: 100%;
}
#app {
	height: 100%;
	width: 100%;
}
</style>
