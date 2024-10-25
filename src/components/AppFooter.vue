<script>
export default {};
</script>

<template>
	<footer class="bg-dark text-light text-center py-4 mt-0">
		<div class="container">
			<h5 class="mb-3">Glossario della Programmazione</h5>
			<p>
				Un progetto di <strong>Mattia Piazzolla</strong> realizzato durante il
				corso di <strong>Boolean</strong>.
			</p>
			<div class="social-icons mt-3">
				<a
					href="https://github.com/mattiapiazzolla"
					target="_blank"
					class="text-light mx-2">
					<i class="fab fa-github"></i>
				</a>
				<a
					href="https://www.linkedin.com/in/mattiapiazzolla"
					target="_blank"
					class="text-light mx-2">
					<i class="fab fa-linkedin"></i>
				</a>
			</div>
			<p class="mt-3">
				© {{ new Date().getFullYear() }} Mattia Piazzolla. Tutti i diritti
				riservati.
			</p>
		</div>
	</footer>
</template>

<style scoped>
footer {
	position: relative;
	bottom: 0;
	width: 100%;
}

.social-icons a {
	font-size: 24px; /* Modifica la dimensione delle icone social */
}

.social-icons i {
	transition: color 0.3s;
}

.social-icons a:hover i {
	color: #007bff; /* Cambia il colore quando l'icona è in hover */
}
</style>
