<script>
import DefinitionCard from "./DefinitionCard.vue";

export default {
	props: {
		section: Object,
	},
	components: {
		DefinitionCard,
	},
};
</script>

<template>
	<div class="def-section my-3 row">
		<div class="col-12">
			<h3 class="mt-5 my-3">{{ section.type.toUpperCase() }}</h3>
			<div class="row g-4">
				<DefinitionCard
					v-for="(definition, index) in section.defs"
					:key="index"
					:def="definition" />
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
.def-section {
	position: sticky;
}
</style>
