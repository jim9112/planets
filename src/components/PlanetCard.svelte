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
        {planet.rotation}
    </div>
    <div class="stat">
        <h4>
            REVOLUTION TIME
        </h4>
        {planet.revolution}
    </div>
    <div class="stat">
        <h4>
            RADIUS
        </h4>
        {planet.radius}
    </div>
    <div class="stat">
        <h4>
            AVERAGE TEMP.
        </h4>
        {planet.temperature}
    </div>
</div>

<style>
    .stat {
        border: 1px solid #979797;
    }
</style>