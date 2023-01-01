<section id="aboutContainer">
  <slot></slot>
</section>

<style>
  #aboutContainer {
    width: calc((672 / 1440) * 100vw);
    height: calc(100vh - 32px);

    display: flex;
    flex-direction: column;
    transform: translateY(100%);
    animation: slideFromBottom 2.25s ease 2s forwards;
  }

  @media screen and (max-width: 768px) {
    #aboutContainer {
      width: 100vw;
      height: 100vh;
      background-color: transparent;
    }
  }
</style>