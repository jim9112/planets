<script lang="ts">
    export let image;
    export let name;
    export let content;
    export let source;
    export let changeMode;
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
                <li on:click={changeMode('overview')}>OVERVIEW</li>
                <li on:click={changeMode('internal')}>INTERNAL STRUCTURE</li>
                <li on:click={changeMode('geology')}>SURFACE GEOLOGY</li>
            </ul>
        </nav>
    </div>
</div>
<style>
    h1 {
        font-size: 80px;
        margin-bottom: 23px;
    }
    p {
        font-size: 14px;
        margin-bottom: 24px;
    }
    nav {
        margin-top: 39px;
    }
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
        align-items: center;
        gap: 220px;
    }
    .description-container {
        max-width: 350px;
        text-align: left;
    }
    nav li {
        cursor: pointer;
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