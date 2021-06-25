<script lang="ts">
    import Overview from '../components/Overview.svelte' 
    export let planet
</script>


<Overview image={planet.images.planet} name={planet.name} content={planet.overview.content} />