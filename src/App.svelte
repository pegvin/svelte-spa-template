<script>
	// Import Page JS for Client Side Routing
	import router from 'page'

	// Importing all the pages
	import Home from './pages/Home.svelte';
	import About from './pages/About.svelte'
	import NotFound from './pages/404.svelte'

	// Importing Navbar
	import Navbar from './components/Header.svelte'

	let page; // This variable will hold the current page to be displayed.
	router('/', () => page = Home) // Set the page variable if the user has navigated to /
	router('/about', () => page = About) // Set the page variable if the user has navigated to /about
	router('/*', () => page = NotFound) // Set the page variable if user has navigated to all possible pages which are not defined above.
	router.start() // Start the Router.
</script>

<Navbar />

<main>
	<!-- Render the component, with the page variable which holds our page to be displayed. -->
	<svelte:component this={page} /> 
</main>
