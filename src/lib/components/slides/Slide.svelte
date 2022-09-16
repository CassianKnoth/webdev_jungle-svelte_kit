<script lang="ts">
  export let isParallax: boolean = false;
</script>

<section class="slide " class:parallax={isParallax}>
  <slot />
</section>

<style>
  .slide {
    width: 100vw;
    padding: var(--gap);
    background-color: var(--color-neutral);

    /* parallax */
    transform-style: preserve-3d;
    position: relative;
  }

  .slide:nth-of-type(odd):not(:first-child) {
    background-color: var(--color-pastel);
  }

  .slide :global(h1) {
    font-size: 2rem;
    margin-bottom: var(--gap);
  }

  @media only screen and (min-width: 600px) {
    .slide :global(h1) {
      font-size: 3rem;
    }
  }

  .parallax {
    /* layout */
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    /* text */
    color: var(--color-neutral);
    text-align: center;
    text-shadow: 0 0 20px var(--color-dark);

    background: none;
  }

  .slide::after {
    background-image: url("/img/jungle.jpg");
    background-size: cover;
  }

  .parallax::after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    transform: translateZ(var(--parallax-shift)) scale(1.1);
    z-index: -1;
  }
</style>
