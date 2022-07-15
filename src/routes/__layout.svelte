<script>
	import '../app.css';
	import Footer from '../components/Footer.svelte';
	import Nav from '../components/Nav.svelte';
</script>

<section class="px-10 mx-auto my-5 items-center py-5">
	<Nav />
	<slot />
	<Footer />
</section>
