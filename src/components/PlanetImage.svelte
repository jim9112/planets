<script lang="ts">
  export let name: string;
  export let image: string;
  export let secondImage: null | string;
</script>


<div class="relative">
  <!-- to do: make planet its own component -->
  <img class={`${name}-image`} src={image} alt="">
  {#if secondImage !== null}
      <img class="second-image-container" src={secondImage} alt="">
  {/if}
</div>

<style>
  .relative {
        position: relative;
    }

    .second-image-container {
        position: absolute;
        width: 168px;
        left: 25%;
        top: 50%;
    }
    /* responsive breakpoints */

    /* phone */
    @media (max-width: 500px) {
        img {
            width: 200px;
            margin: auto;
        }
    }
    

    /* tablet */
    @media (min-width: 651px) {

        /* planet sizing */

        .Mercury-image {
            width: 180px;
        }
        .Venus-image {
            width: 253px;
        }
        .Earth-image {
            width: 285px;
        }
        .Mars-image {
            width: 213px;
        }
        .Jupiter-image {
            width: 369px;
        }
        .Saturn-image {
            width: 422px;
        }
        .Uranus-image {
            width: 290px;
        }
        .Neptune-image {
            width: 285px;
        }
    }

    /* computer */
    @media (min-width: 801px) {
        /* planet sizing */

        .Mercury-image {
            width: 100%;
        }
        .Venus-image {
            width: 100%;
        }
        .Earth-image {
            width: 100%;
        }
        .Mars-image {
            width: 100%;
        }
        .Jupiter-image {
            width: 100%;
        }
        .Saturn-image {
            width: 100%;
        }
        .Uranus-image {
            width: 100%;
        }
        .Neptune-image {
            width: 100%;
        }
    }
</style>