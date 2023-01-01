<script lang="ts">
  import AboutContainer from './lib/AboutContainer.svelte';
  import Footer from './lib/Footer.svelte';
  import SlideshowContainer from './lib/SlideshowContainer.svelte';
  import TitleScreen from './lib/TitleScreen.svelte';

  let website_loaded = false
</script>

<main>
  {#if website_loaded}
    <SlideshowContainer />
    <AboutContainer />
  {:else}
    <TitleScreen />
  {/if}
</main>
<Footer />

<style>
  main {
    display: flex;
    background-color: black;
    color: white;
    overflow: hidden;
  }
</style>