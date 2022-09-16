<script context="module">
  // variables in module are not reactive...
  // open a storage
  import { writable } from "svelte/store";
  let hideFooter = writable(false);

  export const hideLayoutFooter = () => {
    // storage value change syntax
    hideFooter.update((value) => (value = true));
  };
  export const showLayoutFooter = () => {
    // storage value change syntax
    hideFooter.update((value) => (value = false));
  };
</script>

<script lang="ts">
  import "../styles/global.css";
  import Header from "$lib/components/Header.svelte";
  import Footer from "$lib/components/slides/Footer.svelte";
</script>

<Header />
<main>
  <slot />
</main>
{#if !$hideFooter}
  <!-- use $ to reference the value behind a storage name -->
  <Footer />
{/if}

<style>
  main {
    overflow: hidden;
  }
</style>
