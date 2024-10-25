<script>
import FilterSection from "./FilterSection.vue";
import { store } from "../store.js";
export default {
	components: { FilterSection },

	data() {
		return {
			store,
		};
	},
};
</script>

<template>
	<header class="py-2 d-flex justify-content-center">
		<div class="container bg-black text-white py-3 px-5 rounded-5">
			<div class="row">
				<div class="col-4">
					<h3 class="m-0">Glossario</h3>
				</div>
				<div class="col-4 d-flex">
					<input
						class="form-control form-control-sm w-100 rounded-5 text-center p-1"
						type="text"
						placeholder="Cerca definizione"
						@keyup.enter="store.searchDef = $event.target.value" />
				</div>
				<div class="col-4">
					<div class="btn-group float-end rounded-pill">
						<button
							type="button"
							class="btn btn-light dropdown-toggle rounded-pill"
							data-bs-toggle="dropdown"
							data-bs-display="static"
							aria-expanded="false">
							Filtra
						</button>
						<FilterSection @filterByType="store.filterByType" />
					</div>
				</div>
			</div>
		</div>
	</header>
</template>

<style lang="scss" scoped>
.container {
	position: fixed;
	top: 10px;
	z-index: 10000;
	width: 80%;
}
</style>
