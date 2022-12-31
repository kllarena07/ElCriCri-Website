<script lang="ts">
    import pic_theme_0 from '../assets/pic-theme-0.jpeg'
    import pic_theme_1 from '../assets/pic-theme-1.jpeg'
    import pic_theme_2 from '../assets/pic-theme-2.jpeg'
</script>

<section id="slideshow-container">
    <div class="img-wrapper">
        <img src={pic_theme_0} alt="cri cri theme 0" />
    </div>
    <div class="img-wrapper">
        <img src={pic_theme_1} alt="cri cri theme 1" />
    </div>
    <div class="img-wrapper">
        <img src={pic_theme_2} alt="cri cri theme 2" />
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
    height: 100vh;

    display: flex;
    overflow: hidden;
    transform: translateY(-100%);
    animation: slide-from-top var(--loading-speed) ease var(--loading-delay) forwards;
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
</style>