<section id="title-screen">
  <div id="title-btn-wrapper">
    <button>Discover &#8594</button>
  </div>
  <h1>Who is El Cri Cri?</h1>
</section>

<style>
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
  #title-screen {
    width: 100vw;
    height: 100vh;
    display: flex;
    flex-direction: column-reverse;
    justify-content: center;
    align-items: center;
  }
  #title-screen h1 {
    font-size: clamp(2rem, 5rem, 3vw);
    opacity: 0;
    animation: fade-in 2s ease 1s forwards, grow-bigger 2s ease 1s forwards;
    margin-bottom: 1.5rem;
    transition: text-shadow 500ms ease;
  }
  #title-btn-wrapper {
    opacity: 0;
    animation: step-in-from-left 1.5s ease 3s forwards, fade-in 1.5s ease 3s forwards;
  }
  #title-btn-wrapper button {
    padding: .5rem .7rem;
    font-size: 1.15rem;
    font-style: italic;
    border: none;
    background-color: white;
    color: black;
    transition: transform 800ms ease;
  }
  #title-btn-wrapper:hover button {
    transform: scale(1.1);
    transition: 400ms ease;
  }
  #title-btn-wrapper:hover + h1 {
    text-shadow: #FC0 1px 0 7px;
    transition: text-shadow 500ms ease;
  }
  @media screen and (max-width: 1113px) {
    #title-btn-wrapper button {
        font-size: .8rem;
    }
  }
</style>