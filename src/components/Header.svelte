<script lang="ts">
    export let findPlanet: any
</script>
<div class="container">
    <h1>The Planets</h1>
    <ul>
        <li on:click={findPlanet("Mercury")}>MERCURY</li>
        <li on:click={findPlanet("Venus")}>VENUS</li>
        <li on:click={findPlanet("Earth")}>EARTH</li>
        <li on:click={findPlanet("Mars")}>MARS</li>
        <li on:click={findPlanet("Jupiter")}>JUPITER</li>
        <li on:click={findPlanet("Saturn")}>SATURN</li>
        <li on:click={findPlanet("Uranus")}>URANUS</li>
        <li on:click={findPlanet("Neptune")}>NEPTUNE</li>
    </ul>
</div>

<style>
    h1 {
        display: inline;
        margin-left: 33px;
    }
    ul {
        justify-self: end;
        list-style: none;
        display: flex;
        width: max-content;
    }
    li {
        cursor: pointer;
        margin-right: 33px;

    }
    .container {
        display: grid;
        align-items: center;
        grid-auto-flow: column;
        width: 100%;
        border-bottom: 1px solid #979797;
    }
</style>