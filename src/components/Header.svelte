<script lang="ts">
    export let findPlanet: any
    let mobileMenu: any
</script>

<!-- mobile menu -->
<div bind:this={mobileMenu} class="mobile-menu hidden">
    <ul>
        <li on:click={()=> {
            findPlanet("Mercury");
            mobileMenu.classList.add('hidden')
            }}>MERCURY</li>
        <li on:click={()=> {
            findPlanet("Venus");
            mobileMenu.classList.add('hidden')
            }}>VENUS</li>
        <li on:click={()=> {
            findPlanet("Earth");
            mobileMenu.classList.add('hidden')
            }}>EARTH</li>
        <li on:click={()=> {
            findPlanet("Mars");
            mobileMenu.classList.add('hidden')
            }}>MARS</li>
        <li on:click={()=> {
            findPlanet("Jupiter");
            mobileMenu.classList.add('hidden')
            }}>JUPITER</li>
        <li on:click={()=> {
            findPlanet("Saturn");
            mobileMenu.classList.add('hidden')
            }}>SATURN</li>
        <li on:click={()=> {
            findPlanet("Uranus");
            mobileMenu.classList.add('hidden')
            }}>URANUS</li>
        <li on:click={()=> {
            findPlanet("Neptune");
            mobileMenu.classList.add('hidden')
            }}>NEPTUNE</li>
    </ul>
</div>
<!-- actual header -->
<div class="container">
    <h1>The Planets</h1>
    <!-- regular menu -->
    <ul class="desktop-menu">
        <li class="menu-item" on:click={findPlanet("Mercury")}>MERCURY</li>
        <li class="menu-item" on:click={findPlanet("Venus")}>VENUS</li>
        <li class="menu-item" on:click={findPlanet("Earth")}>EARTH</li>
        <li class="menu-item" on:click={findPlanet("Mars")}>MARS</li>
        <li class="menu-item" on:click={findPlanet("Jupiter")}>JUPITER</li>
        <li class="menu-item" on:click={findPlanet("Saturn")}>SATURN</li>
        <li class="menu-item" on:click={findPlanet("Uranus")}>URANUS</li>
        <li class="menu-item" on:click={findPlanet("Neptune")}>NEPTUNE</li>
    </ul>
    <img on:click={()=>{mobileMenu.classList.remove('hidden')}} class="hamburger-icon" src="src/assets/icon-hamburger.svg" alt="">
</div>

<style>
    h1 {
        display: inline;
        margin-left: 33px;
    }
    .container h1 {
        font-family: 'Antonio', sans-serif;
        font-weight: 500;
        font-size: 28px;
    }
    .desktop-menu {
        font-family: 'Spartan', sans-serif;
        font-weight: bold;
        font-size: 11px;
        justify-self: end;
        list-style: none;
        display: flex;
        width: max-content;
    }
    .menu-item {
        cursor: pointer;
        margin-right: 33px;

    }
    .mobile-menu {
        position: absolute;
        top: 0;
        width: 100%;
        height: 100vh;
        padding-top: 40px;
        background: rgba(0, 0, 0, 0.493);
    }
    .mobile-menu ul {
        width: max-content;
    }
    .mobile-menu li {
        cursor: pointer;
    }
    .container {
        display: grid;
        align-items: center;
        grid-auto-flow: column;
        width: 100%;
        border-bottom: 1px solid #979797;
        padding: 16px 0px;
    }
    .hamburger-icon {
        justify-self: end;
        margin-right: 33px;
        display: none;
        cursor: pointer;
    }
    .hidden {
        display: none;
    }
    @media (max-width: 812px) {
        .desktop-menu {
            display: none;
        }
        .hamburger-icon {
            display: inline;
        }
    }
</style>