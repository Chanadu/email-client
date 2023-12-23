<template>
	<q-header elevated class="bg-secondary q-pa-sm" height-hint="98">
		<q-toolbar class="row">
			<!-- <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" /> -->
			<title-header-component></title-header-component>

			<div class="col">
				<tabs-header-component v-if="signedIn"></tabs-header-component>
				<sign-in-header-component v-else></sign-in-header-component>
			</div>

			<search-bar-component></search-bar-component>
		</q-toolbar>
	</q-header>
</template>

<script setup lang="ts">
import SearchBarComponent from "src/components/LayoutComponents/SearchBarComponent.vue";
import TitleHeaderComponent from "src/components/LayoutComponents/HeaderComponents/TitleHeaderComponent.vue";
import TabsHeaderComponent from "src/components/LayoutComponents/HeaderComponents/TabsHeaderComponent.vue";
import SignInHeaderComponent from "src/components/LayoutComponents/HeaderComponents/SignInHeaderComponent.vue";
import { ref } from "vue";

let signedIn = ref(false);
</script>

<style scoped lang="scss">
.tab {
	border-radius: 1.1em;
}
</style>
