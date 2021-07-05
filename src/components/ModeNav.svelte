<script lang="ts">
  export let mode: 'overview' | 'internal' | 'geology'
  export let name: string
  export let changeMode: (mode: string)=>{};
  let passedClass: string
  export {passedClass as class}
</script>

<nav class={`nav-container ${passedClass || ''}`}>
  <ul>
      <li class={mode === 'overview' ? name : ''} on:click={() => changeMode('overview')}>01 OVERVIEW</li>
      <li class={mode === 'internal' ? name : ''} on:click={()=> changeMode('internal')}>02 INTERNAL STRUCTURE</li>
      <li class={mode === 'geology' ? name : ''} on:click={()=>changeMode('geology')}>03 SURFACE GEOLOGY</li>
  </ul>
</nav>


<style>
  nav {
        margin-top: 39px;
    }
    ul {
        list-style: none;
        padding: 0px;
    }
    li {
        font-family: 'Spartan', sans-serif;
        font-weight: bold;
        border: 1px solid #979797;
        margin-bottom: 16px;
        padding: 12px 28px;
    }
    nav li {
        cursor: pointer;
    }

/* planet specific styling */
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
         /* responsive breakpoints */

    /* phone */
    @media (max-width: 500px) {
        .desktop-menu {
          display: none;
        }
    }
    

    /* tablet */
    @media (min-width: 651px) {
        li {
            font-size: 9px;
        }
        .mobile-menu {
          display: none;
        }
    }

    /* computer */
    @media (min-width: 801px) {
        li {
            font-size: 12px;
        }
    }
</style>