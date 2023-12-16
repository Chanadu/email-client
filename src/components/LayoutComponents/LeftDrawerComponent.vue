<template>
	<q-drawer
		show-if-above
		v-model="leftDrawerOpen"
		side="left"
		:mini="miniState"
		@mouseover="miniState = false"
		@mouseout="miniState = true"
		:width="200"
		:breakpoint="500"
		:mini-width="75"
		class="bg-secondary"
		padding
		elevated
	>
		<q-list padding>
			<!-- <q-item-label header class="text-white">Testings</q-item-label>
          <q-separator></q-separator> -->
			<q-item clickable v-ripple>
				<q-item-section avatar>
					<q-icon
						name="inbox"
						draggable="false"
						color="accent"
						size="md"
					></q-icon>
				</q-item-section>
				<q-item-section class="text-body2"> Inbox </q-item-section>
			</q-item>
		</q-list>
	</q-drawer>
</template>

<script setup lang="ts">
import { ref } from "vue";

const leftDrawerOpen = ref(true);
const miniState = ref(true);
</script>

<style scoped lang="scss"></style>
