<script lang="ts">
    import Header from '../components/Header.svelte'
    import PlanetCard  from '../components/PlanetCard.svelte'
    import data from '../lib/data.json'
    let found
    let loading = true
    // find chosen planet in JSON file
    const findPlanet = (planetName) => {
        found = data.find(planet => planet.name === planetName)
        loading = false
        console.log(found)
        
    }
    // To Do: make a default planet pop up
    // found = findPlanet('Earth')
</script>
    <div class="app">
        <Header findPlanet={findPlanet} />
        {#if !loading}
            <PlanetCard planet={found} />
        {/if}
    </div>
    
 

<style>
    .app {
        position: relative;
    }
    :global(*) {
        margin: 0px;
    }
    :global(body) {
        background: #070724;
        background-image: url("../assets/background-stars.svg");
        color: #FFFFFF;
    }
</style>