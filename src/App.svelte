<script lang="ts">
  import './lib/animations.css'
  import AboutContainer from './lib/AboutContainer.svelte';
  import Footer from './lib/Footer.svelte';
  import SlideshowContainer from './lib/SlideshowContainer.svelte';
  import TitleScreen from './lib/TitleScreen.svelte';
  import NavBar from './lib/NavBar.svelte';
  import InfoContainer from './lib/InfoContainer.svelte';

  let websiteLoaded = true
  let theme = 0
</script>

<main>
  {#if websiteLoaded}
    <SlideshowContainer selectedTheme={theme} />
    <AboutContainer>
      <NavBar bind:theme={theme} />
      <InfoContainer selectedTheme={theme} />
    </AboutContainer>
  {:else}
    <TitleScreen bind:websiteLoaded={websiteLoaded} />
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