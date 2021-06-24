<script lang="ts">
    import Header from '../components/Header.svelte'
    import data from '../lib/data.json'
    console.log(data)
</script>

    <Header />
 

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