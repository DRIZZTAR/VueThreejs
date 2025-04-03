<script lang="ts" setup>
import { TresCanvas } from '@tresjs/core';
import { OrbitControls, Levioso, Environment } from '@tresjs/cientos';
</script>

<template>
	<TresCanvas clear-color="#82DBC5" window-size>
		<Suspense fallback="Loading...">
			<Environment background :blur="0.2" preset="city" />
		</Suspense>
		<TresPerspectiveCamera />
		<OrbitControls />
		<TresAmbientLight :intensity="2.0" />
		<Levioso :speed="3" :range="[0.2, 0.25]">
			<TresMesh>
				<TresTorusGeometry :args="[1, 0.5, 16, 32]" />
				<TresMeshStandardMaterial color="blue" metalness="1.2" />
			</TresMesh>
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
