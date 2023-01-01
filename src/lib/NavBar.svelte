<script lang="ts">
  import { createEventDispatcher } from "svelte";
  
  const dispatch = createEventDispatcher()

  let theme = 0
  const setTheme = theme_number => {
    theme = theme_number
    dispatch('theme_change', {
      selected_theme: theme
    })
  }
</script>

<div id='navbar-wrapper'>
  <nav id='navbar'>
      <button class="nav-btn" class:nav-btn-selected="{theme === 0}" on:click={() => { setTheme(0) }}>about</button>
      <button class="nav-btn" class:nav-btn-selected="{theme === 1}" on:click={() => { setTheme(1) }}>work</button>
      <button class="nav-btn" class:nav-btn-selected="{theme === 2}" on:click={() => { setTheme(2) }}>contact</button>
  </nav>
</div>

<style>
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
    font-size: 1rem;
    color: white;
    transition: background-color 100ms ease;
  }
  .nav-btn:not(.nav-btn-selected):hover {
    background-color: rgb(108, 108, 108);
  }
  .nav-btn-selected {
    background-color: white;
    color: black;
  }
</style>