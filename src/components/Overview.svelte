<script lang="ts">
    export let image;
    export let name;
    export let content;
    export let source;
</script>

<div class="planet-container">
    <div class="image-container">
        <img src={image} alt="">
    </div>
    <div class="description-container">
        <h1>{name}</h1>
        <p>{content}</p>
        <span>
            Source : 
            <a href={source} target="blank">Wikapedia</a>
        </span>
        <nav>
            <ul>
                <li>OVERVIEW</li>
                <li>INTERNAL STRUCTURE</li>
                <li>SURFACE GEOLOGY</li>
            </ul>
        </nav>
    </div>
</div>
<style>
    .image-container {
        margin-top: 20px;
        width: 100%;
        display: grid;
        justify-content: center;
    }
    .planet-container {
        text-align: center;
        padding: 24px;
        display: grid;
        grid-auto-flow: column;
        justify-content: center;
        gap: 220px;
    }
    .description-container {
        max-width: 350px;
        text-align: left;
    }
    @media (max-width: 500px) {
        img {
            width: 200px;
            margin: auto;
        }
        .planet-container {
            grid-auto-flow: row;
        }
    }
</style>