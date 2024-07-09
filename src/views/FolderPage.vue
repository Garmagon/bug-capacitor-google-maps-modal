<script setup lang="ts">
import { ref } from 'vue'
import {
	IonButtons,
	IonContent,
	IonHeader,
	IonMenuButton,
	IonPage,
	IonTitle,
	IonToolbar
} from '@ionic/vue'
import BaseButton from '@/components/BaseButton.vue'
import BaseMap from '@/components/BaseMap.vue'
import BaseModal from '@/components/BaseModal.vue'

const isOpen = ref(false)
</script>

<template>
	<ion-page>
		<ion-header :translucent="true">
			<ion-toolbar>
				<ion-buttons slot="start">
					<ion-menu-button color="primary"></ion-menu-button>
				</ion-buttons>
				<ion-title>{{ $route.params.id }}</ion-title>
			</ion-toolbar>
		</ion-header>

		<ion-content :fullscreen="true">
			<ion-header collapse="condense">
				<ion-toolbar>
					<ion-title size="large">{{ $route.params.id }}</ion-title>
				</ion-toolbar>
			</ion-header>

			<div id="container">
				<BaseButton @click="isOpen = true">Modal</BaseButton>
				<BaseMap></BaseMap>
			</div>

			<BaseModal :is-open="isOpen" @close="isOpen = false"></BaseModal>
		</ion-content>
	</ion-page>
</template>

<style scoped>
ion-content {
	--background: transparent;
	background-color: transparent;
}
#container {
	text-align: center;
	position: absolute;
	left: 0;
	right: 0;
	top: 50%;
	transform: translateY(-50%);
}

#container strong {
	font-size: 20px;
	line-height: 26px;
}

#container p {
	font-size: 16px;
	line-height: 22px;
	color: #8c8c8c;
	margin: 0;
}

#container a {
	text-decoration: none;
}
</style>
