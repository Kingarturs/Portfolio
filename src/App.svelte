<script>
	import { Router, Route } from "svelte-navigator";
	import Home from "./routes/Home.svelte";
</script>

<style type="text/scss">
	@import './styles/vars';

	:global(html) {
		height: 100%;
		width: 100%;
		margin: 0;
	}
	:global(body) {
		overflow-y: hidden;
		height: 100%;
		width: 100%;
		margin: 0;
		padding: 0;
		font-family: 'Fira Code', monospace;
		background-color: $background-light;
	}
</style>

<svelte:head>
	<title>Welcome to my Portfolio</title>
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;700&display=swap" rel="stylesheet">
</svelte:head>
<Router>
	<Route path="/" component={Home} primary={false}/>
</Router>
