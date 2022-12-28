<script lang="ts">
  import pic_theme_0 from './assets/pic-theme-0.jpeg'
  import pic_theme_1 from './assets/pic-theme-1.jpeg'
  import pic_theme_2 from './assets/pic-theme-2.jpeg'
    import Counter from './lib/Counter.svelte';

  let theme = 0

  let website_loaded = false

  const setTheme = theme_number => {
    theme = theme_number
  }
</script>

<main>
  {#if website_loaded}
    <section id="slideshow-container" class="section-container">
      <div class="img-wrapper" style="transform: translateX({theme * -100}%)">
        <img src={pic_theme_0} width="768" alt="theme 0" />
      </div>
      <div class="img-wrapper" style="transform: translateX({theme * -100}%)">
        <img src={pic_theme_1} width="768" alt="theme 1" />
      </div>
      <div class="img-wrapper" style="transform: translateX({theme * -100}%)">
        <img src={pic_theme_2} width="768" alt="theme 2" />
      </div>
    </section>
    <section id="about-container" class="section-container">
      <div id='navbar-wrapper'>
        <nav id='navbar'>
            <button class="nav-btn" class:nav-btn-selected="{theme === 0}" on:click={() => { setTheme(0) }}>about</button>
            <button class="nav-btn" class:nav-btn-selected="{theme === 1}" on:click={() => { setTheme(1) }}>work</button>
            <button class="nav-btn" class:nav-btn-selected="{theme === 2}" on:click={() => { setTheme(2) }}>contact</button>
        </nav>
      </div>
      <div id='info-container'>
        {#if theme === 0}
          <h1>Who I am</h1>
          <p>My name is Adrian Corrales. I'm from Mexico, and I really just love music, all of it.</p>
        {/if}
        {#if theme === 1}
          <h1>My works</h1>
          <p>I've released songs on many platforms such as <a href="https://cricrillos.bandcamp.com/" target="_blank" rel="noreferrer">Bandcamp</a>, <a href="https://open.spotify.com/artist/3gZ8L09RcDxRCciQsJcFpU?si=GNf-y-PcSDmHtqmJj3ukRQ" target="_blank" rel="noreferrer">Spotify</a>, <a href="https://music.apple.com/us/artist/el-cri-cri/1628118044" target="_blank" rel="noreferrer">Apple Music</a>, and <a href="https://www.youtube.com/channel/UCeiqfcfLGcq46Xxw-1-js_w" target="_blank" rel="noreferrer">YouTube</a>, and you can hear my latest album <i>Haikus to Myself</i> on all of them. Personally, my favorite song is Efimera</p>
          <iframe title="efimera" src="https://open.spotify.com/embed/track/2nM8yV6i1lxblX0EWirhmV?utm_source=generator" width="100%" height="130" frameBorder="0" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
        {/if}
        {#if theme === 2}
          <h1>My socials</h1>
          <p>You can find me on Instagram at <a href='https://www.instagram.com/crickets.in.spanish/' target="_blank" rel="noreferrer">@crickets.in.spanish</a>. Feel free to send me a DM</p>
        {/if}
      </div>
    </section>
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
    justify-content: center;
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
    opacity: 0;
    animation: fade-in 2s ease 1s forwards;
  }
  #loading-screen h1 {
    font-size: 3vw;
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
    font-size: 1rem;
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
  .section-container {
    background-color: black;
    width: clamp(50vw, 768px, 768px);
    height: 100vh;
  }
  #slideshow-container {
    max-width: 768px;
    margin-right: clamp(0rem, 0rem, 10rem);
    display: flex;
    overflow: hidden;
    animation: slide-from-top 3s ease forwards;
  }
  #slideshow-container * {
    opacity: 0;
    animation: fade-in 800ms ease 1s forwards;
  }
  .img-wrapper {
    width: 768px;
    object-fit: cover;
    transition: 800ms ease;
  }
  @keyframes fade-in {
    from {
      opacity: 0;
    }
    to {
      opacity: 100;
    }
  }
  #about-container {
    max-width: 672px;
    display: flex;
    flex-direction: column;
    animation: slide-from-bottom 3s ease forwards;
  }
  #about-container * {
    opacity: 0;
    animation: fade-in 800ms ease 1s forwards;
  }
  #navbar-wrapper {
    padding: 0 2rem;
  }
  #navbar {
    width: calc(100% - 5rem);
    transform: translateY(90%);
    
    display: flex;
    justify-content: space-between;
    
    border-top: 2px solid white;
    padding: 1rem 2.5rem 0 2.5rem;
  }
  .nav-btn {
    background-color: transparent;
    border: none;
    font-family: 'Source Code Pro', monospace;
    font-size: 1rem;
    color: white;
    box-shadow: inset 0 0 white;
    transition: background-color 100ms ease;
  }
  .nav-btn:not(.nav-btn-selected):hover {
    background-color: rgb(108, 108, 108);
    color: rgb(255, 255, 255);
  }
  .nav-btn-selected {
    background-color: white;
    color: black;
  }
  #info-container {
    margin: auto;
    overflow: hidden;
    padding: 2rem;
  }
  #info-container * {
    animation: fade-in 700ms linear forwards;
  }
  #info-container h1 {
    font-size: 2.5rem;
  }
  #info-container p {
    padding-left: 1rem;
    overflow: hidden;
  }
  #info-container p a {
    color: rgb(183, 26, 239);
    text-decoration-color: rgb(183, 26, 239);
    transition: 400ms ease;
  }
  #info-container p a:hover {
    color: red;
    text-decoration-color: red;
    transition: 400ms ease;
  }
  #info-container iframe {
    margin-top: 1.1rem;
  }
</style>