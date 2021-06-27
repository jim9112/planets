<script lang="ts">
    import Overview from '../components/Overview.svelte' 
    export let planet
    let mode = 'overview'

    const changeMode = (newMode) => {
        mode = newMode
    }
</script>

{#if mode === 'overview'}
    <Overview 
        image={planet.images.planet} 
        name={planet.name} 
        content={planet.overview.content} 
        source={planet.overview.source}
        changeMode={changeMode} 
    /> 
    {:else if mode === 'internal'}  
    <Overview 
        image={planet.images.internal} 
        name={planet.name} 
        content={planet.structure.content} 
        source={planet.structure.source}
        changeMode={changeMode}  
    /> 
    {:else if mode === 'geology'}  
    <Overview 
        image={planet.images.geology} 
        name={planet.name} 
        content={planet.geology.content} 
        source={planet.geology.source}
        changeMode={changeMode} 
    /> 
{/if}

<div class="stat-container">
    <div class="stat">
        <h4>
            ROTATION TIME
        </h4>
        <span>
            {planet.rotation}
        </span>
    </div>
    <div class="stat">
        <h4>
            REVOLUTION TIME
        </h4>
        <span>
            {planet.revolution}
        </span>
    </div>
    <div class="stat">
        <h4>
            RADIUS
        </h4>
        <span>
            {planet.radius}
        </span>
    </div>
    <div class="stat">
        <h4>
            AVERAGE TEMP.
        </h4>
        <span>
            {planet.temperature}
        </span>
    </div>
</div>

<style>
    .stat-container {
        display: grid;
        grid-auto-flow: column;
        justify-content: center;
        gap: 30px;
    }
    .stat {
            border: 1px solid #979797;
            display: grid;
            grid-auto-flow: row;
            width: 255px;
    }
    @media (max-width: 500px) {
        .stat-container {
            grid-auto-flow: row;
        }
        .stat {
            margin: 8px 24px;
            grid-auto-flow: column;
            padding: 10px 24px;
        }
        .stat span {
            justify-self: end;
        }
    }
</style>