<script>
	import Navbar from '../src/components/Navbar.svelte';
	import Tareas from '../src/components/Tareas.svelte';
</script>

<main class="fondo">
	<Navbar />
	<Tareas />
</main>

<style>
	.fondo{
		background: #00c6ff;  /* fallback for old browsers */
		background: -webkit-linear-gradient(to right, #0072ff, #00c6ff);  /* Chrome 10-25, Safari 5.1-6 */
		background: linear-gradient(to right, #0072ff, #00c6ff); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
		height: 100vh;
		background-position: center;
		background-size: cover;
	}
</style>