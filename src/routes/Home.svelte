<script>
    import Switch from "svelte-switch";
    import { Link } from "svelte-navigator";
    // import AppSvg from "../img/app_development.svg"

    let checkedValue = true;
    let location;
    let navigate;

    function handleChange(e) {
    const { checked } = e.detail;
    checkedValue = checked;
    }
</script>

<style type="text/scss">
    @import '../styles/vars';
    :global(.nav-item){
        text-decoration: none;
        color: $textColor-light;
        padding: 2px 10px;
        box-sizing: border-box;
        border-radius: 20px;
    }

    :global(.nav-item):visited{
        color: inherit;
    }

    :global(.nav-item):hover{
        color: $accent-color;
        text-decoration: none;
    }

    .app {
        height: 100%;
        width: 100%;
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
        background-color: $background-light;
        z-index: 1;
    }

    .background {
        position: absolute;
        height: 100%;
        width: 100%;
        -webkit-clip-path: polygon(74% 0, 100% 0, 100% 100%, 65% 100%);
        clip-path: polygon(74% 0, 100% 0, 100% 100%, 65% 100%);
        z-index: -1;
        background-color: $secondary-color;
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
            color: $textColor-light;
            margin: 0;
        }

        .dev-text {
            font-size: 68px;
            color: $secondary-color;
            font-weight: bold;
            margin: 0;
            margin-top: 15px;
        }

        :global(.portfolio-button){
            color: $buttonText-color;
            background-color: $accent-color;
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
            color: $buttonText-color;
        }

        :global(.portfolio-button):hover{
            padding: 12px 36px;
            text-decoration: none;
        }

    .image {
        width: 45%;
        display: flex;
        justify-content: center;
        align-items: center;
    }

</style>

<main class="app">
    <div class="navbar">
        <Link class="nav-item" to="#">Home</Link>
        <Link class="nav-item" to="#">Portfolio</Link>
        <Link class="nav-item" to="#">Blog</Link>
        <Link class="nav-item" to="#">Contact</Link>
        <Switch 
            offColor="#2B303F"
            offHandleColor="#8C50FF"
            onHandleColor="#8C50FF"
            onColor="#F0F0F0"
            unCheckedIcon={false}
            checked={false}
            handleDiameter={""}
        >
            <span slot="checkedIcon" />
            <span slot="unCheckedIcon" />
        </Switch>
    </div>

    <div class="background"></div>

    <div class="content">
        <div class="text">
            <p class="name-text" >Hi! My name's Luis!</p>
            <p class="dev-text" >I'm a Full-Stack Developer</p>
            <Link class="portfolio-button" to="#">Watch my work!</Link>
        </div>
        <div class="image">
            <!-- <img src={AppSvg} alt="Developer" width="80%"> -->
        </div>
    </div>
</main>