<script lang="ts">
    export let image: string;
    export let name: string;
    export let content: string;
    export let source: string;
    export let changeMode: (mode: string)=>{};
    export let mode: 'overview' | 'internal' | 'geology'
    export let secondImage: string | null;

</script>

<div class="planet-container">
    <div class="image-container">
        <div class="relative">

            <img src={image} alt="">
            {#if secondImage !== null}
                <img class="second-image-container" src={secondImage} alt="">
            {/if}
        </div>
    </div>
    <div class="description-container">
        <div>
            <h1>{name}</h1>
            <p>{content}</p>
            <span>
                 Source : 
                <a href={source} target="blank">Wikapedia</a>
            </span>
        </div>

        <nav>
            <ul>
                <li class={mode === 'overview' ? name : ''} on:click={() => changeMode('overview')}>01 OVERVIEW</li>
                <li class={mode === 'internal' ? name : ''} on:click={()=>{              
                    changeMode('internal')
                }}>02 INTERNAL STRUCTURE</li>
                <li class={mode === 'geology' ? name : ''} on:click={()=>changeMode('geology')}>03 SURFACE GEOLOGY</li>
            </ul>
        </nav>
    </div>
</div>

<style>
    h1 {
        font-family: 'Antonio', sans-serif;
        font-weight: 500;
        font-size: 80px;
        margin-bottom: 23px;
    }
    p {
        font-family: 'Spartan', sans-serif ;
        font-size: 14px;
        margin-bottom: 24px;
    }
    span {
        font-family: 'Spartan', sans-serif ;
    }
    ul {
        list-style: none;
        padding: 0px;
    }
    li {
        font-family: 'Spartan', sans-serif;
        font-weight: bold;
        font-size: 12px;
        border: 1px solid #979797;
        margin-bottom: 16px;
        padding: 12px 28px;
    }
    nav {
        margin-top: 39px;
    }
    .image-container {
        margin-top: 20px;
        width: 100%;
        display: grid;
        justify-content: center;
    }
    .second-image-container {
        position: absolute;
        width: 168px;
        left: 25%;
        top: 50%;
    }
    .planet-container {
        text-align: center;
        padding: 24px;
        display: grid;
        grid-auto-flow: column;
        justify-content: center;
        align-items: center;
        gap: 220px;
    }
    .relative {
        position: relative;
    }
    .description-container {
        max-width: 350px;
        text-align: left;
    }
    nav li {
        cursor: pointer;
    }

/* planet specific styling for nav */
    .Mercury {
        background-color: #419EBB;
        border: none;
        cursor: default;
    }

    .Venus {
        background-color: #EDA249;
        border: none;
        cursor: default;
    }

    .Earth {
        background-color: #6D2ED5;
        border: none;
        cursor: default;
    }

    .Mars {
        background-color: #D14C32;
        border: none;
        cursor: default;
    }

    .Jupiter {
        background-color: #D83A34;
        border: none;
        cursor: default;
    }

    .Saturn {
        background-color: #CD5120;
        border: none;
        cursor: default;
    }

    .Uranus {
        background-color: #1EC1A2;
        border: none;
        cursor: default;
    }

    .Neptune {
        background-color: #2D68F0;
        border: none;
        cursor: default;
    }

    @media (max-width: 500px) {
        img {
            width: 200px;
            margin: auto;
        }
        .planet-container {
            grid-auto-flow: row;
        }
    }
</style>