<script lang="ts">
  import picTheme3 from '../assets/pic-theme-3.jpeg'
  import picTheme4 from '../assets/pic-theme-4.jpeg'

  export let selectedTheme = 0;
</script>

<section id="slideshow-container" style="--img-translate: { selectedTheme * -100}%">
  <div id="slide-0" class="slideshow-img-wrapper"></div>
  <div id="slide-1" class="slideshow-img-wrapper"></div>
  <div id="slide-2" class="slideshow-img-wrapper"></div>
</section>

<style>
  #slideshow-container {
    width: calc((768 / 1440) * 100vw);
    --img-translate: -0%;

    display: flex;
    overflow: hidden;
    transform: translateY(-100%);
    animation: slideFromTop 2.25s ease 1.5s forwards;
  }
  .slideshow-img-wrapper {
    width: calc((768 / 1440) * 100vw);
    height: 100vh;
    background-size: cover;
    background-repeat: no-repeat;
    transform: translateX(var(--img-translate));
    flex: 0 0 auto;
    transition: transform 800ms ease;
  }
  #slide-0 {
    background-image: url('../assets/pic-theme-0.jpeg');
  }
  #slide-1 {
    background-image: url('../assets/pic-theme-1.jpeg');
    background-position: 0% 70%;
  }
  #slide-2 {
    background-image: url('../assets/pic-theme-2.jpeg');
    background-position: 0% 30%;
  }

  @media screen and (max-width: 768px) {
    #slideshow-container {
      position: absolute;
      width: 100vw;
      height: 100vh;
    }
    .slideshow-img-wrapper {
      width: 100vw;
      object-fit: cover;
    }
    #slide-1 {
      background-image: url('../assets/pic-theme-3.jpeg');
    }
    #slide-2 {
    background-image: url('../assets/pic-theme-4.jpeg');
    background-position: 0% 50%;
  }
  }
</style>