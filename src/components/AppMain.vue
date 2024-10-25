<script>
import { store } from "../store.js";
import DefinitionSection from "./DefinitionSection.vue";
import FilterSection from "./FilterSection.vue";
export default {
	components: {
		DefinitionSection,
		FilterSection,
	},
	data() {
		return {
			store,
		};
	},
	methods: {
		filterByType(type) {
			store.filterType = type;
		},
	},
	computed: {
		filteredDefinitions() {
			let filterDefinitions = [];
			if (store.searchDef != "" && store.filterType == "all") {
				store.definitions.forEach((item) => {
					let obj = {
						id: item.id,
						type: item.type,
						defs: [],
					};

					item.defs.forEach((def) => {
						if (
							def.name.toLowerCase().includes(store.searchDef.toLowerCase())
						) {
							obj.defs.push(def);

							filterDefinitions.push(obj);
						}
					});
				});

				return filterDefinitions;
			} else if (store.filterType != "all" && store.searchDef == "") {
				filterDefinitions = store.definitions.filter((item) => {
					return item.type === store.filterType;
				});

				return filterDefinitions;
			} else {
				return store.definitions;
			}
		},
	},
};
</script>

<template>
	<body>
		<div class="container">
			<DefinitionSection
				v-for="section in filteredDefinitions"
				:key="section.id"
				:section="section" />
		</div>
	</body>
</template>

<style lang="scss" scoped>
body {
	margin-top: 50px;
	overflow: scroll;
}
</style>
