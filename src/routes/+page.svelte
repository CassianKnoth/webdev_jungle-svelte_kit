<script>
  import Footer from "$lib/components/slides/Footer.svelte";
  import ParallaxWrapper from "$lib/components/slides/ParallaxWrapper.svelte";
  import SlideParallax from "$lib/components/slides/SlideParallax.svelte";
  import SlidePersonal from "$lib/components/slides/SlidePersonal.svelte";
  import SlideTricolon from "$lib/components/slides/SlideTricolon.svelte";

  import { hideLayoutFooter, showLayoutFooter } from "./+layout.svelte";
  import { onMount, onDestroy } from "svelte";

  onMount(async () => {
    hideLayoutFooter();
    console.log("page mount hide footer");
  });

  onDestroy(async () => {
    showLayoutFooter();
    console.log("page destroy show footer");
  });
</script>

<ParallaxWrapper>
  <SlideParallax />
  <!-- empty div with id for scrolling -->
  <div id="next" />
  <SlidePersonal />
  <SlideTricolon />
  <Footer />
</ParallaxWrapper>
