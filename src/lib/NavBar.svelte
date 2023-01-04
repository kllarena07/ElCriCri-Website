<script lang="ts">
  export let theme = 0

  const navBtns = [
    { name: 'about', theme: 0 },
    { name: 'work', theme: 1 },
    { name: 'contact', theme: 2 },
  ]
</script>

<div id='navbar-wrapper'>
  <nav id='navbar'>
    {#each navBtns as btn}
      <button class="nav-btn" class:nav-btn-selected="{theme === btn.theme}" on:click={() => theme = btn.theme}>{btn.name}</button>
    {/each}
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