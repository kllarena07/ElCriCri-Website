<script lang="ts">
  import pic_theme_0 from '../assets/pic-theme-0.jpeg'
  import pic_theme_1 from '../assets/pic-theme-1.jpeg'
  import pic_theme_2 from '../assets/pic-theme-2.jpeg'
  import pic_theme_4 from '../assets/pic-theme-4.jpeg'
  import pic_theme_5 from '../assets/pic-theme-5.jpeg'
</script>

<section id="slideshow-container">
  <div class="img-wrapper">
    <img src={pic_theme_0} alt="cri cri theme 0" />
  </div>
  <div class="img-wrapper">
    <img class="desktop-img" src={pic_theme_1} alt="cri cri theme 1" />
    <img class="mobile-img" src={pic_theme_4} alt="cri cri theme 4" />
  </div>
  <div class="img-wrapper">
    <img class="desktop-img" src={pic_theme_2} alt="cri cri theme 2" />
    <img class="mobile-img" src={pic_theme_5} alt="cri cri theme 3" />
  </div>
</section>

<style>
  @keyframes slide-from-top {
    from {
        transform: translateY(-100%);
    }
    to {
        transform: translateY(0);
    }
  }
  #slideshow-container {
    width: calc((768 / 1440) * 100vw);
    --img-translate: -0%;

    display: flex;
    overflow: hidden;
    transform: translateY(-100%);
    animation: slide-from-top 2.25s ease 1.5s forwards;
  }
  .img-wrapper {
    width: calc((768 / 1440) * 100vw);
    height: 100vh;
    object-fit: cover;
    transform: translateX(var(--img-translate));
    flex: 0 0 auto;
    transition: transform 800ms ease;
  }
  .img-wrapper img {
    width: 100%;
    height: 100%;
  }
  .mobile-img {
    display: none;
  }

  @media screen and (max-width: 768px) {
    #slideshow-container {
      position: absolute;
      width: 100vw;
      height: 100vh;
    }
    .img-wrapper {
      width: 100vw;
      object-fit: cover;
    }
    .desktop-img {
      display: none;
    }
    .mobile-img {
      display: block;
    }
  }
</style>