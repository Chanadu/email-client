<template>
	<q-layout view="hHh Lpr lFf" class="bg-primary text-white">
		<header-component></header-component>
		<left-drawer-component></left-drawer-component>

		<q-page-container>
			<router-view></router-view>
		</q-page-container>
	</q-layout>
</template>

<script setup lang="ts">
import HeaderComponent from "src/components/LayoutComponents/HeaderComponent.vue";
import LeftDrawerComponent from "src/components/LayoutComponents/LeftDrawerComponent.vue";
</script>

<style lang="scss" scoped></style>
