<script>
    import { Link } from "svelte-navigator";
    import Switch from "svelte-switch";
    import DarkMode from "svelte-dark-mode";

    let theme;

    $: checkedValue = theme === "dark" ? true : false;
    $: document.body.className = theme; // "dark" or "light"

	let checkedValue = true;
	let open = false;

	function handleChange(e) {
        const { checked } = e.detail;
        checkedValue = checked;
        theme = checkedValue === true ? "dark" : "light"
    }

    function switchMenuState() {
        open = !open;
    }
</script>

<style type="text/scss">
    :global(body.dark) {
        --bg: #181818;
        --color: white;
        --secondary-color: #979797;
        --accent: #F4CE2C;
        --border: #424242;
        --menu-bg: #2c2c2c;
        --secondary: #FF3838;
    }

    :global(body.light) {
        --bg: #F8F8F8;
        --color: #353535;
        --secondary-color: #696969;
        --accent: #f4cf2c;
        --border: #dadada;
        --menu-bg: #e7e7e7;
        --secondary: #FF2424;
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
        list-style: none;
    }

	.navbar {
        box-sizing: border-box;
        padding: 0 3rem;
        width: 100%;
        height: 3.9rem;
        display: flex;
        align-items: center;
        font-weight: 600;
        font-size: 15px;
        justify-content: space-between;
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

    .mobile {
        display: none;
    }

    .spacing {
        display: inline-flex;
        gap: 1.5rem;
    }

    .menu {
        transition: all 0.2s ease-out;
        overflow: hidden;
        box-sizing: border-box;
        height: 0;
        display: flex;
        flex-direction: column;
        align-items: center;
        background-color: var(--menu-bg);
        display: none;
        
        :global(.mobile-item) {
            color: var(--color);
            font-size: 0.9rem;
            width: 100%;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 3rem;
            font-weight: bold;
            margin: 0;
        }

        :global(.mobile-item):hover {
            text-decoration: none;
        }
    }
    .open {
        height: 12rem;
    }

    @media screen and (max-width: 768px) {
        .navbar {
            padding: 0 2rem;
            overflow: hidden;
        }

        .spacing {
            display: inline-flex;
            gap: 1rem;
        }

        :global(.nav-icon){
            padding: 0 0.5rem;
        }
    }

    @media screen and (max-width: 550px) {
        .desktop {
            display: none;
        }

        .mobile {
            display: block;
        }

        .menu {
            display: block;
        }
    }

</style>

<svelte:head>
    {#if checkedValue}
		<meta name="theme-color" content="#181818">
    {:else}
		<meta name="theme-color" content="#F8F8F8">
	{/if}
</svelte:head>
<nav class="navbar">
    <DarkMode bind:theme />
    <div class="nav-section spacing">
        <a href="https://www.linkedin.com/in/luis-arturo" aria-label="Linkedin" rel="noreferrer" class="nav-icon" target="_blank">
            <i class="fab fa-linkedin"></i>
        </a>
        <a href="https://github.com/Kingarturs" aria-label="Github" rel="noreferrer" class="nav-icon" target="_blank">
            <i class="fab fa-github"></i>
    </div>

    <div class="mobile nav-section" on:click={switchMenuState}>
        <div class="nav-icon">
            <i class="fas fa-bars"></i>
        </div>
    </div>

    <div class="desktop nav-section">
        <Link class="nav-item" to="/">Home</Link>
        <Link class="nav-item" to="/portfolio">Portfolio</Link>
        <Link class="nav-item" to="/about">About</Link>
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
</nav>

<div class={"menu" + (open ? " open" : "")}>
    <Link class="mobile-item" to="/" on:click={switchMenuState} >Home</Link>
    <Link class="mobile-item" to="/portfolio" on:click={switchMenuState} >Portfolio</Link>
    <Link class="mobile-item" to="/about" on:click={switchMenuState} >About</Link>
    <div class="mobile-item">
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