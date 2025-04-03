<script lang="ts" setup>
import { TresCanvas } from '@tresjs/core';
import { OrbitControls, Levioso, Environment, Tetrahedron, Precipitation, Text3D } from '@tresjs/cientos';
</script>

<template>
	<TresCanvas window-size>
		<Environment :background="true" :blur="0.2" preset="sunset" />
		<TresPerspectiveCamera />
		<OrbitControls />
		<TresAmbientLight :intensity="2.0" />
    <Precipitation
      :randomness="0"
      :speed="1"
      :count="2500"
    />
    <TresGridHelper :args="[10, 10]" :position="[0,-1.5,0]"/>
		<Levioso :speed="3" :range="[0.0, 1.0]" :rotationFactor="5.0">
  		<Tetrahedron :args="[1, 0]">
        <TresMeshStandardMaterial :color="0x000000" :metalness="1.5" :roughness="0.0"/>
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
