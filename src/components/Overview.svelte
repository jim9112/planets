<script lang="ts">
    export let image;
    export let name;
    export let content;
</script>

<div class="planet-container">
    <div class="image-container">
        <img src={image} alt="">
    </div>
    <h1>{name}</h1>
    <p>{content}</p>
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