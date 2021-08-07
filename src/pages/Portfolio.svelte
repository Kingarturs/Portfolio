<script>
    import ProjectCard from '../components/ProjectCard.svelte';
    import { projects } from '../data/Projects.json';
</script>

<style type="text/scss">
    .portfolio-container {
        height: calc(100vh - 4rem);
        width: 100%;
        display: flex;
        flex-direction: column;

        .title-container {
            width: 100%;
            padding: 0 3rem;
            color: var(--color);
            box-sizing: border-box;
            
            .title {
                font-size: 1.5rem;
                font-weight: bold;
                margin: 0;
            }
            
            .subtitle {
                font-size: 0.9rem;
                font-weight: 400;
                margin: 0;
            }
            
            .click {
                color: var(--secondary);
                font-weight: bold;
            }
        }

        .cards-container {
            width: 100%;
            height: 100%;
            padding: 0 3rem;
            display: inline-flex;
            gap: 30px;
            box-sizing: border-box;
            flex-wrap: wrap;
            padding-bottom: 2rem;
        }
    }

    @media screen and (max-width: 768px) {
        .portfolio-container {
            height: auto;

            .title-container {
                margin-top: 2rem;
                align-items: center;
                padding: 0 2rem;
                text-align: center;
            }

            .cards-container {
                justify-content: center;
                padding: 0 1rem;
                padding-bottom: 4rem;
            }
        }
        
    }
</style>

<svelte:head>
    <title>Luis Arturo | Portfolio</title>
</svelte:head>

<section class="portfolio-container">
    <div class="title-container">
        <h1 class="title">Projects</h1>
        <p class="subtitle">Here is some of my work! <span class="click">Click one for details!</span></p>
    </div>
    <div class="cards-container">
        {#each projects as project}
            <ProjectCard project={project}/>
        {/each}
    </div>
</section>
