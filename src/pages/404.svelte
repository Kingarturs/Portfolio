<style type="text/scss">

    .not-found {
        height: calc(100vh - 4rem);
        width: 100%;
        box-sizing: border-box;
        padding: 0 3rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        color: var(--color);

        .image {
            width: 40%;
        }

        .title {
            font-size: 2rem;
            font-weight: bold;
            margin: 0;
            margin-top: 2rem;
        }

        .subtitle {
            font-size: 1.2rem;
            margin: 0;
            text-align: center;
        }
    }

    @media screen and (max-width: 768px) {
        .not-found {
            .image {
                width: 100%;
            }
    
            .title {
                font-size: 1.4rem;
            }

            .subtitle {
                font-size: 1rem;
                text-align: center;
            }
        }
    }

</style>

<svelte:head>
    <title>Luis Arturo | Not Found</title>
</svelte:head>
<section class="not-found">
    <img class="image" src="./images/404.svg" alt="Not found">
    <p class="title">404 Not Found</p>
    <p class="subtitle">I couln't find the page you were looking for</p>
</section>