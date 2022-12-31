<script lang="ts">
  import pic_theme_0 from './assets/pic-theme-0.jpeg'
  import pic_theme_1 from './assets/pic-theme-1.jpeg'
  import pic_theme_2 from './assets/pic-theme-2.jpeg'
  
  import AboutContainer from './AboutContainer.svelte';
  import SlideshowContainer from './SlideshowContainer.svelte';

  let website_loaded = true
</script>

<main>
  {#if website_loaded}
    <SlideshowContainer />
    <AboutContainer />
  {:else}
    <section id="loading-screen">
      <h1>Who is El Cri Cri?</h1>
      <div id="btn-wrapper">
        <button on:click={() => { website_loaded = true }}>Find out</button>
      </div>
    </section>
  {/if}
</main>

<style>  
  @import url('https://fonts.googleapis.com/css2?family=Source+Code+Pro&display=swap'); 
  main {
    display: flex;
    background-color: black;
    font-family: 'Source Code Pro', monospace;
    color: white;
    overflow: hidden;
  }
  #loading-screen {
    width: 100vw;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  @keyframes grow-bigger {
    from {
      transform: scale(0.95)
    }
    to {
      transform: scale(1)
    }
  }
  #loading-screen h1 {
    font-size: 3vw;
    opacity: 0;
    animation: fade-in 2s ease 1s forwards, grow-bigger 2s ease 1s forwards;
    margin: 1.5rem 0;
  }
  @keyframes slide-from-left {
    from {
      transform: translateX(-10%);
    }
    to {
      transform: translateX(0%);
    }
  }
  #btn-wrapper {
    opacity: 0;
    animation: slide-from-left 1.5s ease 3s forwards, fade-in 1.5s ease 3s forwards;
  }
  #loading-screen button {
    font-family: 'Source Code Pro', monospace;
    padding: .5rem .7rem;
    font-size: clamp(.2rem, 1rem, 2.5vw);
    font-style: italic;
    border: none;
    background-color: white;
    color: black;
    transition: 800ms ease;
  }
  #loading-screen button:hover {
    transform: scale(1.1);
    transition: 400ms ease;
  }

  @keyframes slide-from-top {
    from {
      transform: translateY(-100%);
    }
    to {
      transform: translateY(0);
    }
  }
  @keyframes slide-from-bottom {
    from {
      transform: translateY(100%);
    }
    to {
      transform: translateY(0);
    }
  }
  @keyframes fade-in {
    from {
      opacity: 0;
    }
    to {
      opacity: 100;
    }
  }
</style>