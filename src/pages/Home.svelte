<script>
    import { Link } from "svelte-navigator";
    const src = "../images/app_development.svg";
</script>

<style type="text/scss">
    .home {
        height: calc(100vh - 4rem);
        width: 100%;
        display: flex;
        flex-direction: column;
    }

    .splash-screen {
        padding: 0 3rem;
        box-sizing: border-box;
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: row;
        flex-shrink: 0;
        overflow: hidden;
    }

    .skills {
        padding: 0px 4rem;
        box-sizing: border-box;
        width: 100%;
        height: 100vh;
        display: flex;
        flex-direction: row;
        flex-shrink: 0;
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

    .shape {
        background: linear-gradient(45deg, var(--secondary) 10%, var(--accent) 100%);
        animation: morph 8s ease-in-out infinite;
        border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%;
        height: auto;
        transition: all 1s ease-in-out;
        width: 100%;
        z-index: 5;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        color: white;
        padding: 2rem;
        min-height: 300px;
    }

    @keyframes morph {
        0% {
            border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%;
            background-position: 0% 0%;
            background-size: 200%;
        }

        50% {
            border-radius: 40% 60% 70% 40% / 50% 60% 30% 60%;
            background-position: 100% 100%;
            background-size: 200%;
        }

        100% {
            border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%;
            background-position: 0% 0%;
            background-size: 200%;
        }
    }
    
    #image {
        align-items: center;
        display: flex;
        width: 40%;
        height: auto;
        justify-content: center;
    }

    @media screen and (max-width: 768px) {
        .splash-screen {
            flex-direction: column;
            width: 100%;
            height: auto;
            padding: 2rem;
            
            #image {
                width: 100%;
                margin-top: 4rem;
            
                .shape {
                    width: 100%;
                }
                
                img {
                    width: 90%;
                }
            }

            .text {
                width: 100%;
                align-items: center;

                .name-text {
                    font-size: 2rem;
                    text-align: center;
                    width: 100%;
                }

                .dev-text {
                    font-size: 3.5rem;
                    text-align: center;
                    width: 100%;
                }
            }
        }
        .splash-screen {
            flex-direction: column;
            width: 100%;
            height: auto;
            padding: 2rem;
            
            #image {
                width: 100%;
                margin-top: 4rem;
            
                .shape img {
                    width: 80%;
                }
            }

            .text {
                .name-text {
                    font-size: 1.5rem;
                    text-align: center;
                    width: 100%;
                }

                .dev-text {
                    font-size: 3rem;
                    text-align: center;
                    width: 100%;
                }
            }
        }
    }

    @media screen and (max-width: 320px) {
        .splash-screen {
            #image {
            
                .shape img {
                    width: 120%;
                }
            }
        }
    }

</style>

<svelte:head>
    <title>Luis Arturo | Web Developer</title>
</svelte:head>
<main class="home">
    <section class="splash-screen">
        <!-- <div in:fly="{{duration: 400, x: 700}}" class="background" /> -->
        <div class="text">
            <p class="name-text" >Hi! My name's Luis!</p>
            <p class="dev-text" >I'm a Web Developer</p>
            <Link class="portfolio-button" to="/portfolio">Watch my work</Link>
        </div>
        
        <div id="image">
            <div class="shape">
                <img src={src} alt="Animation">
            </div>
        </div>
    </section>
    <!-- <section class="skills">
    </section> -->
</main>