<script lang="ts">
  import ThemeContainer from "./ThemeContainer.svelte";

  export let selectedTheme = 0;
</script>

<div id='infoContainer'>
  <ThemeContainer themeNumber={0} selectedTheme={selectedTheme}>
    <h1>Who I am</h1>
    <p>My name is Adrian Corrales. I'm from Mexico, and I really just love music, all of it.</p>
  </ThemeContainer>
  <ThemeContainer themeNumber={1} selectedTheme={selectedTheme}>
    <h1>My works</h1>
    <p>I've released music on <a href="https://cricrillos.bandcamp.com/" target="_blank" rel="noreferrer">Bandcamp</a>, <a href="https://open.spotify.com/artist/3gZ8L09RcDxRCciQsJcFpU?si=GNf-y-PcSDmHtqmJj3ukRQ" target="_blank" rel="noreferrer">Spotify</a>, <a href="https://music.apple.com/us/artist/el-cri-cri/1628118044" target="_blank" rel="noreferrer">Apple Music</a>, and <a href="https://www.youtube.com/channel/UCeiqfcfLGcq46Xxw-1-js_w" target="_blank" rel="noreferrer">YouTube</a>.</p>
    <p>You can hear my latest album <i>Haikus to Myself</i> on all of them.</p>
    <p>While I recommend the entire album, "Efimera" is definitely one of my favorite songs.</p>
    <iframe title="efimera" src="https://open.spotify.com/embed/track/2nM8yV6i1lxblX0EWirhmV?utm_source=generator" width="100%" height="130" frameBorder="0" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/U3MZsmpEA58" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
  </ThemeContainer>
  <ThemeContainer themeNumber={2} selectedTheme={selectedTheme}>
    <h1>My socials</h1>
    <p>You can find me on Instagram at <a href='https://www.instagram.com/crickets.in.spanish/' target="_blank" rel="noreferrer">@crickets.in.spanish</a>. Feel free to send me a DM.</p>
  </ThemeContainer>
</div>

<style>
  #infoContainer {
    max-width: 672px;
    margin: auto;
    padding: 2rem;
  }
  #infoContainer > * {
    animation: fadeIn 700ms linear forwards;
  }
  #infoContainer h1 {
    font-size: 2.5rem;
  }
  #infoContainer p {
    padding-left: 1rem;
  }
  #infoContainer a {
    color: rgb(183, 26, 239);
    text-decoration-color: rgb(183, 26, 239);
    transition: text-decoration-color 400ms ease, color 400ms ease;
  }
  #infoContainer a:hover {
    color: red;
    text-decoration-color: red;
    transition: text-decoration-color 400ms ease, color 400ms ease;
  }
  #infoContainer iframe {
    margin-top: 1.1rem;
  }
  @media screen and (max-width: 768px) {
    #infoContainer {
      transform: translateY(14%);
    }
  }
</style>