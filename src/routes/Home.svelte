<script>
    import { Link } from "svelte-navigator";
    
    const src = "../images/app_development.svg";

    export let location;
    export let navigate;
</script>

<style type="text/scss">
    @import '../styles/vars';

    .app {
        height: 100%;
        width: 100%;
    }

    .background {
        position: absolute;
        height: 100%;
        width: 100%;
        -webkit-clip-path: polygon(74% 0, 100% 0, 100% 100%, 65% 100%);
        clip-path: polygon(74% 0, 100% 0, 100% 100%, 65% 100%);
        z-index: -1;
        background-color: var(--secondary);
    }

    .content {
        padding: 0px 80px;
        box-sizing: border-box;
        position: absolute;
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: row;
    }

    .text {
        width: 55%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
    }
        .name-text {
            font-size: 38px;
            color: var(--color);
            margin: 0;
        }

        .dev-text {
            font-size: 68px;
            color: var(--secondary);
            font-weight: bold;
            margin: 0;
            margin-top: 15px;
        }

        :global(.portfolio-button){
            color: white;
            background-color: var(--accent);
            text-decoration: none;
            font-weight: bold;
            font-size: 16px;
            border-radius: 10px;
            padding: 12px 20px;
            box-sizing: border-box;
            margin-top: 15px;
            transition: padding .1s;
            transition-timing-function: ease;
        }

        :global(.portfolio-button):visited{
            color: white;
        }

        :global(.portfolio-button):hover{
            padding: 12px 36px;
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

    <div class="background"></div>

    <div class="content">
        <div class="text">
            <p class="name-text" >Hi! My name's Luis!</p>
            <p class="dev-text" >I'm a Full-Stack Developer</p>
            <Link class="portfolio-button" to="#">Watch my work!</Link>
        </div>
        <div id="image">
            <img width="80%" src={src} alt="dev animation">
        </div>
    </div>
</main>