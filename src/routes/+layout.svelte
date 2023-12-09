<script>
	import Navbar from '$lib/components/Navbar.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import FooterInfo from '$lib/components/FooterInfo.svelte';

	import '../app.pcss';
</script>

<Navbar />
<slot />
<FooterInfo />
<Footer />
