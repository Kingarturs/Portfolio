<script>
    export let project;
</script>

<style>
    h1 {
        font-size: 1.6rem;
        margin: 1rem 0 0.2rem 0;
    }
        
    h2 {
        font-size: 1.1rem;
        margin: 0.4rem 0;
    }

    img {
        width: 100%;
        border-radius: 10px;
    }

    p {
        font-size: 0.8rem;
        margin: 0;
    }

    a {
        color: rgb(53, 192, 211);
    }

    a:hover {
        text-decoration: none;
    }

    .modal-content {
        height: 100%;
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    :global(.content) {
        background-color: var(--bg);
        color: var(--color);
        padding: 2rem !important;
    }

    .secondary-color {
        color: var(--secondary-color);
    }

    @media screen and (max-width: 768px) {
        h1 {
            width: 100%;
            text-align: center;
        }
            
        h2 {
            width: 100%;
            text-align: center;
        }

        p {
            width: 100%;
            text-align: center;
        }

        a p {
            font-size: 1rem;
        }
    }
</style>

<div class="modal-content">
    <img src={project.image} alt={project.title}>
    
    <div>
        <h1>{project.title}</h1>
        {#if project.url}
            <a href={project.url} rel="noreferrer">
                <p>Take a look!</p>
            </a>
        {/if}

        <h2>Description</h2>
        <p class="secondary-color">{project.description}</p>
        
        <h2>What i learned</h2>
        <p class="secondary-color">{project.learned}</p>
    </div>
</div>
