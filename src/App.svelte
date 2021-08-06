<script>
	import { Router, Route } from "svelte-navigator";
	import Navbar from "./components/Navbar.svelte";
    import Home from "./pages/Home.svelte";
    import Portfolio from "./pages/Portfolio.svelte";
	import Modal from 'svelte-simple-modal';
</script>

<style type="text/scss">
	:global(html) {
		height: 100%;
		width: 100%;
		margin: 0;
		box-sizing: border-box;
	}
	:global(body) {
		overflow-y: auto;
		height: 100%;
		width: 100%;
		margin: 0;
		padding: 0;
		font-family: 'Poppins', sans-serif;
		background-color: var(--bg);
        overflow-x: hidden;
        box-sizing: border-box;
		transition: all 0.2s ease-out;
	}

</style>

<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@200;400;600&display=swap" rel="stylesheet">
    <script src="https://kit.fontawesome.com/0f61084166.js" crossorigin="anonymous"></script>
</svelte:head>
<Router>
    <Navbar />
	<Modal>
		<Route path="/" component={Home} primary={true}/>
		<Route path="/portfolio" component={Portfolio} primary={false}/>
	</Modal>
</Router>
