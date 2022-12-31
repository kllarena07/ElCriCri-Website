<section id="slideshow-container">
    <div class="img-wrapper" style="transform: translateX({0 * -100}%)"></div>
    <div class="img-wrapper" style="transform: translateX({1 * -100}%)"></div>
    <div class="img-wrapper" style="transform: translateX({2 * -100}%)"></div>
</section>

<style>
    #slideshow-container {
        width: calc((768 / 1440) * 100%);
        height: 100vh;
        background-color: blue;

        display: flex;
        overflow: hidden;
        opacity: 0;
    }
    .img-wrapper {
        object-fit: cover;
        transition: 800ms ease;
    }
</style>