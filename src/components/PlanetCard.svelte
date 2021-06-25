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
    <div>
        <h4>
            ROTATION TIME
        </h4>
        {planet.rotation}
    </div>
    <div>
        <h4>
            REVOLUTION TIME
        </h4>
        {planet.revolution}
    </div>
    <div>
        <h4>
            RADIUS
        </h4>
        {planet.radius}
    </div>
    <div>
        <h4>
            AVERAGE TEMP.
        </h4>
        {planet.temperature}
    </div>
</div>