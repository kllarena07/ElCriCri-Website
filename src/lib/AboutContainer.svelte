<section id="about-container">
  <slot></slot>
</section>

<style>
  #about-container {
    width: calc((672 / 1440) * 100vw);
    height: calc(100vh - 32px);

    display: flex;
    flex-direction: column;
    transform: translateY(100%);
    animation: slide-from-bottom 2.25s ease 2s forwards;
  }

  @media screen and (max-width: 768px) {
    #about-container {
      width: 100vw;
      height: 100vh;
      background-color: transparent;
    }
  }
</style>