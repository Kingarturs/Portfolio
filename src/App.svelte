<script>
	import { Router, Link, Route } from "svelte-navigator";
	import Switch from "svelte-switch";
    import Home from "./pages/Home.svelte";
    import DarkMode from "svelte-dark-mode";

    let theme;

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
        --bg: #272727;
        --color: white;
        --accent: #F4CE2C;
        --border: #747474;
        --secondary: #FF2424;
    }

    :global(body.light) {
        --bg: #F8F8F8;
        --color: #353535;
        --accent: #f4cf2c;
        --border: #e4e4e4;
        --secondary: #FF2424;
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
		font-family: 'Poppins', sans-serif;
		background-color: var(--bg);
        overflow-x: hidden;
        box-sizing: border-box;
	}

    :global(.nav-item){
        text-decoration: none;
        color: var(--color);
        padding: 2px 10px;
        box-sizing: border-box;
        border-radius: 20px;
        margin-right: 1.5rem;
    }

    :global(.nav-item):visited{
        color: inherit;
    }

    :global(.nav-item):hover{
        color: var(--secondary);
        text-decoration: none;
    }
    
    :global(.nav-section){
        display: flex;
        align-items: center;
        justify-content: space-around;
    }

	.navbar {
        box-sizing: border-box;
        padding: 0 3rem;
        width: 100%;
        height: 4rem;
        display: flex;
        align-items: center;
        font-weight: 600;
        font-size: 15px;
        justify-content: space-between;
        background-color: var(--bg);
        color: var(--color);
    }

    :global(.nav-icon){
        text-decoration: none;
        color: var(--color) !important;
        font-size: 1.5rem;
        padding: 0 0.5rem;
        border-radius: 5px;
    }

    :global(.nav-icon):hover{
        background-color: var(--border);
    }


    .spacing {
        display: inline-flex;
        gap: 1.5rem;
    }

</style>

<svelte:head>
	<title>Luis Arturo | Web Developer</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@200;400;600&display=swap" rel="stylesheet">
    <script src="https://kit.fontawesome.com/0f61084166.js" crossorigin="anonymous"></script>
</svelte:head>
<Router>
    <DarkMode bind:theme />
	<div class="navbar">
        <div class="nav-section spacing">
            <a href="https://www.linkedin.com/in/luis-arturo" class="nav-icon" target="_blank">
                <i class="fab fa-linkedin"></i>
            </a>
            <a href="https://github.com/Kingarturs" class="nav-icon" target="_blank">
                <i class="fab fa-github"></i>
            </a>
        </div>
        <div class="nav-section">
            <Link class="nav-item" to="#">Home</Link>
            <Link class="nav-item" to="#">Portfolio</Link>
            <Link class="nav-item" to="#">Contact</Link>
            <Switch 
                offColor="#2B303F"
                offHandleColor="#FF2424"
                onHandleColor="#FF2424"
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
    </div>

	<Route path="/" component={Home} primary={false}/>
</Router>
