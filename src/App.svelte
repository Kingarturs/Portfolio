<script>
	import { Router, Link, Route } from "svelte-navigator";
	import Switch from "svelte-switch";
    import Home from "./routes/Home.svelte";
    import DarkMode from "svelte-dark-mode";

    let theme;

    $: switchTheme = theme === "dark" ? "light" : "dark";
    $: checkedValue = theme === "dark" ? true : false;
    $: document.body.className = theme; // "dark" or "light"

	let checkedValue = true;

	function handleChange(e) {
        const { checked } = e.detail;
        checkedValue = checked;
        theme = checkedValue === true ? "dark" : "light"
    }
</script>

<style type="text/scss">

    :global(body.dark) {
        --bg: #323239;
        --color: white;
        --accent: #8C50FF;
        --border: #747474;
        --secondary: #2EB0D9;
    }

    :global(body.light) {
        --bg: #F8F8F8;
        --color: #2B303F;
        --accent: #8C50FF;
        --border: #DDDDDD;
        --secondary: #2EB0D9;
    }

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
		background-color: var(--bg);
	}

    :global(.nav-item){
        text-decoration: none;
        color: var(--color);
        padding: 2px 10px;
        box-sizing: border-box;
        border-radius: 20px;
    }

    :global(.nav-item):visited{
        color: inherit;
    }

    :global(.nav-item):hover{
        color: var(--accent);
        text-decoration: none;
    }

	.navbar {
        position: absolute;
        right: 0;
        box-sizing: border-box;
        margin-top: 30px;
        margin-right: 60px;
        padding: 10px;
        width: 500px;
        height: 50px;
        display: flex;
        border-radius: 30px;
        border: #DDDDDD solid 2px;
        align-items: center;
        justify-content: space-around;
        background-color: var(--bg);
        color: var(--color);
        border-color: var(--border);
        z-index: 1;
    }

</style>

<svelte:head>
	<title>Welcome to my Portfolio</title>
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;700&display=swap" rel="stylesheet">
</svelte:head>
<Router>
    <DarkMode bind:theme />
	<div class="navbar">
        <Link class="nav-item" to="#">Home</Link>
        <Link class="nav-item" to="#">Portfolio</Link>
        <Link class="nav-item" to="#">Blog</Link>
        <Link class="nav-item" to="#">Contact</Link>
        <Switch 
            offColor="#2B303F"
            offHandleColor="#8C50FF"
            onHandleColor="#8C50FF"
            onColor="#DDD"
            unCheckedIcon={false}
            checked={checkedValue}
            handleDiameter={""}
            on:change={handleChange}
        >
            <span slot="checkedIcon" />
            <span slot="unCheckedIcon" />
        </Switch>
    </div>
	<Route path="/" component={Home} primary={false}/>
</Router>
