<script lang="ts">
    import Overview from '../components/Overview.svelte' 
    export let planet
</script>


<Overview 
    image={planet.images.planet} 
    name={planet.name} 
    content={planet.overview.content} 
    source={planet.overview.source} 
/>

<div>
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
    
    @media (max-width: 500px) {
        .stat {
            border: 1px solid #979797;
            margin: 8px 24px;
            display: grid;
            grid-auto-flow: column;
            padding: 10px 24px;
        }
        .stat span {
            justify-self: end;
        }
    }
</style>