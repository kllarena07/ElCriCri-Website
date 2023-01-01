<script lang="ts">
  export let theme = 0

  const navBtns = [
    { name: 'about', theme: 0 },
    { name: 'work', theme: 1 },
    { name: 'contact', theme: 2 },
  ]
</script>

<div id='navbarWrapper'>
  <nav id='navbar'>
    {#each navBtns as btn}
      <button class="navBtn" class:navBtnSelected="{theme === btn.theme}" on:click={() => theme = btn.theme}>{btn.name}</button>
    {/each}
  </nav>
</div>

<style>
  #navbarWrapper {
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
  .navBtn {
    background-color: transparent;
    border: none;
    font-size: 1rem;
    color: white;
    transition: background-color 100ms ease;
  }
  .navBtn:not(.navBtnSelected):hover {
    background-color: rgb(108, 108, 108);
  }
  .navBtnSelected {
    background-color: white;
    color: black;
  }
</style>