<script lang="ts">
    export let planet
</script>
<div class="planet-container">
    <div class="image-container">
        <img src={planet.images.planet} alt="">
    </div>
    <h1>{planet.name}</h1>
    <p>{planet.overview.content}</p>
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
    }
    @media (max-width: 812px) {
        img {
            width: 200px;
            margin: auto;
        }
    }
</style>