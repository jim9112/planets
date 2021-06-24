<script lang="ts">
    export let findPlanet: any
</script>
<h1>The Planets</h1>
<ul>
    <li on:click={findPlanet("Mercury")}>Mercury</li>
    <li on:click={findPlanet("Venus")}>Venus</li>
    <li on:click={findPlanet("Earth")}>Earth</li>
    <li on:click={findPlanet("Mars")}>Mars</li>
    <li on:click={findPlanet("Jupiter")}>Jupiter</li>
    <li on:click={findPlanet("Saturn")}>Saturn</li>
    <li on:click={findPlanet("Uranus")}>Uranus</li>
    <li on:click={findPlanet("Neptune")}>Neptune</li>
</ul>