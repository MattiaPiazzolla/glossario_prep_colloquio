<script>
export default {
	props: {
		def: Object,
	},
};
</script>

<template>
	<div class="col-12 col-md-6 col-lg-4 col-xl-3">
		<div class="card">
			<div class="card-header">
				<h5 class="card-title m-0">{{ def.name }}</h5>
			</div>
			<div class="card-body">
				<p v-html="def.description" class="card-text"></p>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
.card {
	height: 300px;
	position: relative;
	transition: all 0.15s ease-in-out;

	&:hover {
		cursor: pointer;
		transform: scale(1.075);
	}
}
.card-header {
	position: absolute;
	width: 100%;
	background-color: black;
	color: white;
}

.card-body {
	overflow: scroll;
	margin-top: 50px;
}
</style>
