<script>
    export let project;

    import { getContext } from 'svelte';
    import ProjectModal from '../components/ProjectModal.svelte';

    const { open } = getContext('simple-modal');

    const openModal = (project) => {
        open(
            ProjectModal,
            { project: project },
            { styleCloseButton: 
                { 
                    backgroundColor: "#FF2424",
                    border: "none",
                    top: "0.5rem",
                    right: "0.5rem",
                }
            }
        );
    }
</script>

<style type="text/scss">
    .project-container {
        width: 16rem;
        height: fit-content;
        overflow: hidden;
        border-radius: 10px;
        border: 2px solid var(--border);
        color: var(--color);
        transition: all 0.1s ease-out;
        
        .project-image {
            width: 100%;
            height: 8rem;
            object-fit: cover;
        }

        .project-data {
            padding: 0.5rem 1rem 0 1rem;
            height: 5rem;

            .project-title {
                font-weight: bold;
                font-size: 0.9rem;
                margin: 0;
                text-overflow: ellipsis;
                white-space: nowrap;
                overflow: hidden;
            }

            .project-description {
                font-size: 0.8rem;
                margin: 0;
                color: var(--secondary-color);
                overflow: hidden;
            }
        }
        
        .tag-container {
            padding: 1rem 1rem;
            display: inline-flex;
            width: 100%;
            gap: 8px;
            overflow-x: auto;
            -ms-overflow-style: 0 !important;
            scrollbar-width: 0 !important;
            
            .tag {
                padding: 0.2rem 0.5rem;
                border-radius: 1rem;
                background-color: red;
                font-size: 0.8rem;
                font-weight: bold;
                color: white
            }
        }
        .tag-container::-webkit-scrollbar {
            display: none;
        }
    }

    .project-container:hover {
        transform: scale(1.02);
        cursor: pointer;
    }

    @media screen and (max-width: 412px) {
        .project-container {
            width: 85%;
        }        
    }

</style>

<div class="project-container" on:click={() => openModal(project)}>
    <img class="project-image" src={project.image} alt={project.title}>
    <div class="project-data">
        <p class="project-title">{project.title}</p>
        <p class="project-description">{project.description}</p>
    </div>
    <div class="tag-container">
        {#each project.tags as tag}
            <span class={"tag " + tag.class}>{tag.name}</span>
        {/each  }
    </div>
</div>