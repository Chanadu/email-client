<template>
	<q-header elevated class="bg-secondary q-pa-sm" height-hint="98">
		<q-toolbar class="row">
			<!-- <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" /> -->
			<div class="col-1"></div>
			<q-toolbar-title class="col-shrink">
				<q-avatar>
					<q-icon name="home" size="md" />
				</q-avatar>
				Email Client
			</q-toolbar-title>
			<q-tabs class="col q-mx-lg" align="justify">
				<q-route-tab to="/page1" label="Page One" class="tab" />
				<q-route-tab to="/page2" label="Page Two" class="tab" />
				<q-route-tab to="/page3" label="Page Three" class="tab" />
			</q-tabs>
			<search-bar-component></search-bar-component>
		</q-toolbar>
	</q-header>
</template>

<script setup lang="ts">
import SearchBarComponent from "src/components/LayoutComponents/SearchBarComponent.vue";
</script>

<style scoped lang="scss">
.tab {
	border-radius: 1.1em;
}
</style>
