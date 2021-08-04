<script>
    import { Link } from "svelte-navigator";
    import { fly } from 'svelte/transition';
    const src = "../images/app_development.svg";

    export let location;
    export let navigate;
</script>

<style type="text/scss">
    .app {
        height: 100%;
        width: 100%;
        display: flex;
        flex-direction: column;
        overflow-y: auto;
    }

    /* Hide scrollbar for Chrome, Safari and Opera */
    .app::-webkit-scrollbar {
        display: none;
    }

    /* Hide scrollbar for IE, Edge and Firefox */
    .app {
        -ms-overflow-style: none;  /* IE and Edge */
        scrollbar-width: none;  /* Firefox */
    }

    /* .background {
        position: absolute;
        top:0;
        left:0;
        right:0;
        bottom:0;
        height: 100%;
        width: 100%;
        -webkit-clip-path: polygon(55% 0, 100% 0, 100% 100%, 80% 100%);
        clip-path: polygon(55% 0, 100% 0, 100% 100%, 80% 100%);
        background: linear-gradient(10deg, var(--accent), var(--secondary));
        z-index: -1;
    } */

    .splash-screen {
        padding: 0 3rem;
        box-sizing: border-box;
        width: 100%;
        height: calc(100vh - 4rem);
        display: flex;
        flex-direction: row;
        flex-shrink: 0;
        position: relative;
        z-index: 0;
    }

    .skills {
        padding: 0px 4rem;
        box-sizing: border-box;
        width: 100%;
        height: 100vh;
        display: flex;
        flex-direction: row;
        flex-shrink: 0;
        position: relative;
        z-index: 0;
    }

    .text {
        width: 55%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        color: var(--color);
    }
        .name-text {
            font-size: 2rem;
            color: var(--color);
            margin: 0;
        }

        .dev-text {
            font-size: 3.8rem;
            color: var(--secondary);
            font-weight: bold;
            margin: 0;
            margin-top: 15px;
            line-height: 1.2;
        }

        :global(.portfolio-button){
            color: var(--secondary);
            background-color: var(--bg);
            text-decoration: none;
            font-weight: bold;
            font-size: 16px;
            border-radius: 10px;
            border: solid 2px var(--secondary);
            padding: 10px 20px;
            box-sizing: border-box;
            margin-top: 15px;
            transition: padding .1s;
            transition-timing-function: ease;
        }

        :global(.portfolio-button):visited{
            color: var(--secondary);
        }

        :global(.portfolio-button):hover{
            padding: 10px 36px;
            text-decoration: none;
        }

    #image {
        width: 45%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

</style>

<main class="app">
    <div class="splash-screen">
        <!-- <div in:fly="{{duration: 400, x: 700}}" class="background" /> -->
        <div class="text">
            <p class="name-text" >Hi! My name's Luis!</p>
            <p class="dev-text" >I'm a Full-Stack Developer</p>
            <Link class="portfolio-button" to="#">Watch my work</Link>
        </div>
        
        <div id="image">
            <img width="85%" src={src} alt="Animation">
        </div>
    </div>
    <!-- <div class="skills">
    </div> -->
</main>