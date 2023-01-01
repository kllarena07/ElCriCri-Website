<script lang="ts">
  import './lib/animations.css'
  import AboutContainer from './lib/AboutContainer.svelte';
  import Footer from './lib/Footer.svelte';
  import SlideshowContainer from './lib/SlideshowContainer.svelte';
  import TitleScreen from './lib/TitleScreen.svelte';
  import NavBar from './lib/NavBar.svelte';
  import InfoContainer from './lib/InfoContainer.svelte';

  let website_loaded = false
  const handleWebsiteLoad = evt => {
    website_loaded = evt.detail.load_condition
  }

  let theme = 0
  const handleThemeChange = evt => {
    theme = evt.detail.selected_theme
  }
</script>

<main>
  {#if website_loaded}
    <SlideshowContainer selected_theme={theme} />
    <AboutContainer>
      <NavBar on:theme_change={handleThemeChange} />
      <InfoContainer selected_theme={theme} />
    </AboutContainer>
  {:else}
    <TitleScreen on:load_website={handleWebsiteLoad} />
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