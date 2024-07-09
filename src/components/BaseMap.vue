<script setup lang="ts">
import { ref } from 'vue'
import { GoogleMap } from '@capacitor/google-maps'
import BaseButton from '@/components/BaseButton.vue'

const map = ref<HTMLDivElement | null>(null)

const createMap = async () => {
	if (!map.value) return

	await GoogleMap.create({
		id: 'my-map', // Unique identifier for this map instance
		element: map.value, // reference to the capacitor-google-map element
		apiKey: '<GOOGLE_MAPS_API_KEY>', // Your Google Maps API Key
		config: {
			center: {
				// The initial position to be rendered by the map
				lat: 33.6,
				lng: -117.9
			},
			zoom: 8 // The initial zoom level to be rendered by the map
		}
	})
}
</script>

<template>
	<BaseButton @click="createMap">Open map</BaseButton>
	<capacitor-google-map ref="map"></capacitor-google-map>
</template>

<style scoped lang="scss">
capacitor-google-map {
	display: inline-block;
	width: 275px;
	height: 400px;
}
</style>
