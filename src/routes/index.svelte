<script lang="ts">
    import Header from '../components/Header.svelte'
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

    <Header findPlanet={findPlanet} />
    {#if !loading}
	<h1>{found?.name}</h1>
{/if}
    
 

<style>
    :global(*) {
        margin: 0px;
    }
    :global(body) {
        background: #070724;
        background-image: url("../assets/background-stars.svg");
        color: #FFFFFF;
    }
</style>