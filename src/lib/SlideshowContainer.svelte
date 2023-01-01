<script lang="ts">
  import picTheme0 from '../assets/pic-theme-0.jpeg'
  import picTheme1 from '../assets/pic-theme-1.jpeg'
  import picTheme2 from '../assets/pic-theme-2.jpeg'
  import picTheme3 from '../assets/pic-theme-3.jpeg'
  import picTheme4 from '../assets/pic-theme-4.jpeg'

  export let selectedTheme = 0;
</script>

<section id="slideshowContainer" style="--img-translate: { selectedTheme * -100}%">
  <div class="slideshowImgWrapper">
    <img src={picTheme0} alt="cri cri theme 0" />
  </div>
  <div class="slideshowImgWrapper">
    <img class="slideshowDesktopImg" src={picTheme1} alt="cri cri theme 1" />
    <img class="slideshowMobileImg" src={picTheme3} alt="cri cri theme 3" />
  </div>
  <div class="slideshowImgWrapper">
    <img class="slideshowDesktopImg" src={picTheme2} alt="cri cri theme 2" />
    <img class="slideshowMobileImg" src={picTheme4} alt="cri cri theme 4" />
  </div>
</section>

<style>
  #slideshowContainer {
    width: calc((768 / 1440) * 100vw);
    --img-translate: -0%;

    display: flex;
    overflow: hidden;
    transform: translateY(-100%);
    animation: slideFromTop 2.25s ease 1.5s forwards;
  }
  .slideshowImgWrapper {
    width: calc((768 / 1440) * 100vw);
    height: 100vh;
    object-fit: cover;
    transform: translateX(var(--img-translate));
    flex: 0 0 auto;
    transition: transform 800ms ease;
  }
  .slideshowImgWrapper img {
    width: 100%;
    height: 100%;
  }
  .slideshowMobileImg {
    display: none;
  }

  @media screen and (max-width: 768px) {
    #slideshowContainer {
      position: absolute;
      width: 100vw;
      height: 100vh;
    }
    .slideshowImgWrapper {
      width: 100vw;
      object-fit: cover;
    }
    .slideshowDesktopImg {
      display: none;
    }
    .slideshowMobileImg {
      display: block;
    }
  }
</style>