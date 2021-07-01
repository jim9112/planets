<script lang="ts">
    export let findPlanet: any
    let mobileMenu: any

    // handle mobil menu clicks
    const menuClick = (planet: string) => {
        findPlanet(planet);
        mobileMenu.classList.add('hidden')
    }
</script>

<!-- mobile menu -->
<div bind:this={mobileMenu} class="mobile-menu hidden">
    <ul>
        <li on:click={()=> menuClick('Mercury')}>MERCURY</li>
        <li on:click={()=> menuClick('Venus')}>VENUS</li>
        <li on:click={()=> menuClick('Earth')}>EARTH</li>
        <li on:click={()=> menuClick('Mars')}>MARS</li>
        <li on:click={()=> menuClick('Jupiter')}>JUPITER</li>
        <li on:click={()=> menuClick('Saturn')}>SATURN</li>
        <li on:click={()=> menuClick('Uranus')}>URANUS</li>
        <li on:click={()=> menuClick('Neptune')}>NEPTUNE</li>
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
    .container {
        display: grid;
        align-items: center;
        width: 100%;
        border-bottom: 1px solid #979797;
        padding: 16px 0px;
    }
    .container h1 {
        font-family: 'Antonio', sans-serif;
        font-weight: 500;
        font-size: 28px;
        display: inline;
        margin-left: 33px;
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
    .hamburger-icon {
        justify-self: end;
        margin-right: 33px;
        display: none;
        cursor: pointer;
    }
    .hidden {
        display: none;
    }

    /* responsive breakpoints */

    /* phone */
    @media (max-width: 650px) {
        .container {
            grid-auto-flow: column;
        }
        .desktop-menu {
            display: none;
        }
        .hamburger-icon {
            display: inline;
        }
    }

    /* tablet */
    @media (min-width: 651px) {
        .container {
            grid-auto-flow: row;
            justify-content: center;
            text-align: center;
            gap: 39px;
        }
    }

    /* computer */
    @media (min-width: 801px) {
        .container {
            grid-auto-flow: column;
            text-align: left;
            justify-content: normal;
            gap: 0px;
        }
    }
</style>