<template>
	<q-input
		dark
		filled
		color="accent"
		label-color="white"
		bg-color="grey-9"
		class="col-3 text-white text-body2 q-mr-md"
		v-model="searchText"
		label="Search"
		clearable
		clear-icon="close"
		icon-color="accent"
		type="search"
	>
		<template v-slot:prepend>
			<q-icon name="search" color="accent"></q-icon>
		</template>
	</q-input>
</template>

<script setup lang="ts">
import { ref } from "vue";

const searchText = ref("");
</script>

<style scoped lang="scss"></style>
