<script lang="ts">
    import { onMount } from 'svelte';
    import Header from '../components/Header.svelte'
    import PlanetCard  from '../components/PlanetCard.svelte'
    import data from '../lib/data.json'
    let found: any
    let loading = true
    
    // find chosen planet in JSON file
    const findPlanet = (planetName: string) => {
        found = data.find(planet => planet.name === planetName)
        loading = false 
    }

    // make a default planet pop up
    onMount(() => {
		findPlanet('Mercury')
	});

</script>

    <svelte:head>
        <link rel="preconnect" href="https://fonts.googleapis.com">
        <link rel="preconnect" href="https://fonts.gstatic.com">
        <link href="https://fonts.googleapis.com/css2?family=Antonio:wght@500&family=Spartan:wght@400;800&display=swap" rel="stylesheet"> 
    </svelte:head>
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