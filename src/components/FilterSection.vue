<script>
import { store } from "../store.js";

export default {
	data() {
		return {
			store,
		};
	},

	methods: {
		filterByType(type) {
			this.$emit("filterByType", type);
		},
	},
};
</script>

<template>
	<div class="dropdown-menu mt-3 dropdown-menu-lg-end p-2 rounded-5 bg-dark">
		<div class="row">
			<div class="col-6">
				<div class="card rounded-5 text-center my-1 dropdown-item">
					<button class="btn" @click="filterByType('all')">TUTTI</button>
				</div>
				<div
					class="card rounded-5 text-center my-1 dropdown-item"
					v-for="section in store.definitions.filter(
						(_, index) => index % 2 === 0
					)"
					:key="section.id">
					<button class="btn" @click="filterByType(section.type)">
						{{ section.type.toUpperCase() }}
					</button>
				</div>
			</div>
			<div class="col-6">
				<div
					class="card rounded-5 text-center my-1 dropdown-item"
					v-for="section in store.definitions.filter(
						(_, index) => index % 2 === 1
					)"
					:key="section.id">
					<button class="btn" @click="filterByType(section.type)">
						{{ section.type.toUpperCase() }}
					</button>
				</div>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
.dropdown-menu {
	width: 500px;
}
</style>
