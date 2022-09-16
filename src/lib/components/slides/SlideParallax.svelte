<script lang="ts">
  import ScrollDownIndicator from "../animation/ScrollDownIndicator.svelte";
  import Slide from "./Slide.svelte";
</script>

<Slide isParallax={true}>
  <h1 class="parallaxHeadline">Welcome to the jungle!</h1>
  <p class="monospace">the webdev jungle...</p>
  <ScrollDownIndicator />
</Slide>

<style>
  h1.parallaxHeadline {
    font-family: "Playfair Display", serif;
    font-size: 2.5rem;
    font-weight: bold;
    margin-bottom: 1rem;
  }

  p {
    font-size: 1.2rem;
  }

  @media only screen and (min-width: 600px) {
    h1.parallaxHeadline {
      font-size: 4rem;
    }

    p {
      font-size: 1.5rem;
    }
  }

  @media only screen and (min-width: 1200px) {
    h1.parallaxHeadline {
      font-size: 5rem;
    }
  }
</style>
