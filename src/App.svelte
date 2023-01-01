<script lang="ts">
  import AboutContainer from './lib/AboutContainer.svelte';
  import SlideshowContainer from './lib/SlideshowContainer.svelte';

  let website_loaded = false
</script>

<main>
  {#if website_loaded}
    <SlideshowContainer />
    <AboutContainer />
  {:else}
    <section id="loading-screen">
      <div id="loading-btn-wrapper">
        <button on:click={() => { website_loaded = true }}>Discover &#8594</button>
      </div>
      <h1 id="loading-title">Who is El Cri Cri?</h1>
    </section>
  {/if}
</main>

<style>  
  @import url('https://fonts.googleapis.com/css2?family=Source+Code+Pro&display=swap');

  @keyframes fade-in {
    from {
      opacity: 0;
    }
    to {
      opacity: 100;
    }
  }
  @keyframes grow-bigger {
    from {
      transform: scale(0.95)
    }
    to {
      transform: scale(1)
    }
  }
  @keyframes step-in-from-left {
    from {
      transform: translateX(-10%);
    }
    to {
      transform: translateX(0%);
    }
  }

  main {
    --img-translate: -0%;
    --loading-delay: 1.5s;
    --loading-speed: 2.25s;
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
    flex-direction: column-reverse;
    justify-content: center;
    align-items: center;
  }
  #loading-screen h1 {
    font-size: clamp(2rem, 5rem, 3vw);
    opacity: 0;
    animation: fade-in 2s ease 1s forwards, grow-bigger 2s ease 1s forwards;
    margin-bottom: 1.5rem;
    transition: text-shadow 500ms ease;
  }
  #loading-btn-wrapper {
    opacity: 0;
    animation: step-in-from-left 1.5s ease 3s forwards, fade-in 1.5s ease 3s forwards;
  }
  #loading-btn-wrapper button {
    font-family: 'Source Code Pro', monospace;
    padding: .5rem .7rem;
    font-size: 1.15rem;
    font-style: italic;
    border: none;
    background-color: white;
    color: black;
    transition: transform 800ms ease;
  }
  #loading-btn-wrapper:hover button {
    transform: scale(1.1);
    transition: 400ms ease;
  }
  #loading-btn-wrapper:hover + h1 {
    text-shadow: #FC0 1px 0 7px;
    transition: text-shadow 500ms ease;
  }

  @media screen and (max-width: 1113px) {
    #loading-btn-wrapper button {
      font-size: .8rem;
    }
  }
</style>