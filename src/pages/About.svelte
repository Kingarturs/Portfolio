<script>

</script>

<style type="text/scss">
    .about {
        width: 100%;
        height: calc(100vh - 4rem);
        padding: 0 6rem;
        display: flex;
        box-sizing: border-box;
    }

    .avatar {
        height: fit-content;
        margin-top: 2rem;
        background: linear-gradient(45deg, var(--secondary) 10%, var(--accent) 100%);
        width: 400px;
        height: 400px;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 50%;
        flex-shrink: 0;
    }
    
    .image {
        width: 300px;
    }

    .text {
        margin-left: 2rem;
        overflow: hidden;
        display: flex;
        flex-direction: column;
        color: var(--color);
    
        .title {
            margin: 0;
            margin-top: 2rem;
            font-weight: bold;
            font-size: 1.8rem;
        }

        .subtitle {
            margin: 0;
            font-weight: bold;
            font-size: 1.2rem;
            color: var(--secondary-color);
            padding-bottom: 1rem;
        }

        .me {
            margin: 0;
            color: var(--secondary-color);
            padding-top: 0.6rem;
        }
        
        .contact-button {
            margin-top: 1rem;
            padding: 0.5rem 1rem;
            font-size: 1.1rem;
            border-radius: 5px;
            color: white;
            background-color: var(--secondary);
            width: fit-content;
            font-weight: bold;
        }

        .contact-button:hover {
            text-decoration: none;
            opacity: 0.9;
        }
    }

    @media screen and (max-width: 768px) {
        .about {
            flex-direction: column;
            padding: 0 2rem;
            padding-bottom: 4rem;
            height: auto;
            align-items: center;
        }
        
        .avatar {
            width: 100%;
            height: min-content;
        }
        
        .image {
            width: 70%;
        }

        .text {
            margin-left: 0;
            text-align: center;
            align-items: center;
        }
    }
</style>

<svelte:head>
    <title>Luis Arturo | About</title>
</svelte:head>
<section class="about">
    <div class="avatar">
        <img class="image" src="./images/avatar.png" alt="avatar">
    </div>

    <div class="text">
        <p class="title">About me</p>
        <p class="subtitle">Learn a little bit about me</p>
        <p class="me">
            I'm a web developer in love with learning constantly, music and videogames.
        </p>
        <p class="me">
            Professionally i'm focused on "full-stack" development but i'm also really interested in SRE and DevOps. I like putting attention to detail and getting better constantly.
        </p>
        <a class="contact-button" href="mailto:kingarturs21@gmail.com">
            Contact me
        </a>
    </div>
</section>