<script lang="ts">
  export let websiteLoaded = false;
</script>

<section id="titleScreen">
  <div id="titleBtnWrapper">
    <button on:click={() => websiteLoaded = true}>Discover &#8594</button>
  </div>
  <h1>Who is El Cri Cri?</h1>
</section>

<style>
  #titleScreen {
    width: 100vw;
    height: 100vh;
    display: flex;
    flex-direction: column-reverse;
    justify-content: center;
    align-items: center;
  }
  #titleScreen h1 {
    font-size: clamp(2rem, 5rem, 3vw);
    opacity: 0;
    animation: fadeIn 2s ease 1s forwards, growBigger 2s ease 1s forwards;
    margin-bottom: 1.5rem;
    transition: text-shadow 500ms ease;
  }
  #titleBtnWrapper {
    opacity: 0;
    animation: stepInFromLeft 1.5s ease 3s forwards, fadeIn 1.5s ease 3s forwards;
  }
  #titleBtnWrapper button {
    padding: .5rem .7rem;
    font-size: 1.15rem;
    font-style: italic;
    border: none;
    background-color: white;
    color: black;
    transition: transform 800ms ease;
  }
  #titleBtnWrapper:hover button {
    transform: scale(1.1);
    transition: 400ms ease;
  }
  #titleBtnWrapper:hover + h1 {
    text-shadow: #FC0 1px 0 7px;
    transition: text-shadow 500ms ease;
  }
  @media screen and (max-width: 1113px) {
    #titleBtnWrapper button {
        font-size: .8rem;
    }
  }
</style>