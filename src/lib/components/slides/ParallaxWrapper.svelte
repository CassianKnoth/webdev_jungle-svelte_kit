<script lang="ts">
</script>

<div class="parallaxWrapper">
  <slot />
</div>

<style>
  .parallaxWrapper {
    height: 100vh;
    overflow-x: hidden;
    overflow-y: auto;
    perspective: var(--parallax-depth);
  }
</style>
