<script lang="ts">
  let theme = 0

  const setTheme = theme_number => {
    theme = theme_number
  }
</script>

<main>
  <section id="slideshow-container" class="section-container">
    <span>this is the slideshow side</span>
  </section>
  <section id="info-container" class="section-container">
    <div class='navbar-wrapper'>
      <nav class='navbar'>
          <button class="nav-btn" class:nav-btn-selected="{theme === 0}" on:click={() => { setTheme(0) }}>about</button>
          <button class="nav-btn" class:nav-btn-selected="{theme === 1}" on:click={() => { setTheme(1) }}>work</button>
          <button class="nav-btn" class:nav-btn-selected="{theme === 2}" on:click={() => { setTheme(2) }}>contact</button>
      </nav>
  </div>
  </section>
</main>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Source+Code+Pro&display=swap');
  .section-container {
    color: white;
    font-family: 'Source Code Pro', monospace;
    background-color: black;
    width: clamp(50vw, 768px, 768px);
    height: 100vh;
  }
  #slideshow-container {
    max-width: 768px;
    float: left;
  }
  #info-container {
    max-width: 672px;
    float: right;
  }
  .navbar-wrapper {
    padding: 0 2rem;
}
.navbar {
    width: calc(100% - 5rem);
    
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
.nav-btn:focus {
  box-shadow: inset 0 -100vh white;
  transition: 400ms ease;
  color: black;
}
.nav-btn:not(.nav-btn-selected):hover {
    background-color: rgb(108, 108, 108);
    color: rgb(255, 255, 255);
}
.nav-btn-selected {
    background-color: white;
    color: black;
}
</style>

<!--
  <div class="slideshow-img-wrapper">
    <img src='../public/images/pic-theme-0.jpeg' alt="theme 0" />
  </div>
    <div class="slideshow-img-wrapper">
      <img src='../public/images/pic-theme-1.jpeg' alt="theme 1" />
    </div>
    <div class="slideshow-img-wrapper">
      <img src='../public/images/pic-theme-2.jpeg' alt="theme 2" />
    </div>

  .slideshow-img-wrapper {
    width: 100%;
    object-fit: cover;
    transform: translateX(0%);
    transition: transform 800ms ease;
  }  
  .slideshow-img-wrapper img {
    max-width: 100%;
    -webkit-user-drag: none;
  }
-->