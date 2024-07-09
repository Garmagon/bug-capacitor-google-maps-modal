<script setup lang="ts">
import { IonButton } from '@ionic/vue'

defineEmits<{
	(e: 'click'): void
}>()
</script>

<template>
	<ion-button @click="$emit('click')"><slot></slot></ion-button>
</template>
