<script setup lang="ts">
import {
	IonButtons,
	IonButton,
	IonModal,
	IonHeader,
	IonToolbar,
	IonContent,
	IonTitle
} from '@ionic/vue'

defineProps<{
	isOpen: boolean
}>()

defineEmits<{
	(e: 'close'): void
}>()
</script>

<template>
	<ion-modal :is-open="isOpen">
		<ion-header>
			<ion-toolbar>
				<ion-title>Modal</ion-title>
				<ion-buttons slot="end">
					<ion-button @click="$emit('close')">Close</ion-button>
				</ion-buttons>
			</ion-toolbar>
		</ion-header>
		<ion-content class="ion-padding">
			<p>
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni illum quidem
				recusandae ducimus quos reprehenderit. Veniam, molestias quos, dolorum consequuntur
				nisi deserunt omnis id illo sit cum qui. Eaque, dicta.
			</p>
		</ion-content>
	</ion-modal>
</template>
