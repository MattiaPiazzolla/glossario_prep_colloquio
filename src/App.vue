<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import AppFooter from "./components/AppFooter.vue";

export default {
	components: {
		AppHeader,
		AppMain,
		AppFooter,
	},
};
</script>

<template>
	<body class="d-flex flex-column justify-content-between">
		<AppHeader />
		<AppMain />
		<AppFooter />
	</body>
</template>

<style lang="scss" scoped>
body {
	height: 100vh;
}
</style>
