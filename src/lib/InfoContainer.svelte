<script lang="ts">
  export let selectedTheme = 0;
</script>

<div id='info-container'>
  {#if selectedTheme === 0}
    <h1>Who I am</h1>
    <p>My name is Adrian Corrales. I'm from Mexico, and I really just love music, all of it.</p>
  {:else if selectedTheme === 1}
    <h1>My works</h1>
    <p>I've released songs on <a href="https://cricrillos.bandcamp.com/" target="_blank" rel="noreferrer">Bandcamp</a>, <a href="https://open.spotify.com/artist/3gZ8L09RcDxRCciQsJcFpU?si=GNf-y-PcSDmHtqmJj3ukRQ" target="_blank" rel="noreferrer">Spotify</a>, <a href="https://music.apple.com/us/artist/el-cri-cri/1628118044" target="_blank" rel="noreferrer">Apple Music</a>, and <a href="https://www.youtube.com/channel/UCeiqfcfLGcq46Xxw-1-js_w" target="_blank" rel="noreferrer">YouTube</a>, and you can hear my latest album <i>Haikus to Myself</i> on all of them.</p>
    <p>If you are wondering what song to listen to first, I would recommend Efimera, my personal favorite.</p>
    <iframe title="efimera" src="https://open.spotify.com/embed/track/2nM8yV6i1lxblX0EWirhmV?utm_source=generator" width="100%" height="130" frameBorder="0" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
  {:else if selectedTheme === 2}
    <h1>My socials</h1>
    <p>You can find me on Instagram at <a href='https://www.instagram.com/crickets.in.spanish/' target="_blank" rel="noreferrer">@crickets.in.spanish</a>. Feel free to send me a DM</p>
  {/if}
</div>

<style>
  #info-container {
    max-width: 672px;
    margin: auto;
    padding: 2rem;
  }
  #info-container > *:not(#info-blanket) {
    animation: fade-in 700ms linear forwards;
  }
  #info-container h1 {
    font-size: 2.5rem;
  }
  #info-container p {
    padding-left: 1rem;
  }
  #info-container a {
    color: rgb(183, 26, 239);
    text-decoration-color: rgb(183, 26, 239);
    transition: text-decoration-color 400ms ease, color 400ms ease;
  }
  #info-container a:hover {
    color: red;
    text-decoration-color: red;
    transition: text-decoration-color 400ms ease, color 400ms ease;
  }
  #info-container iframe {
    margin-top: 1.1rem;
  }
  @media screen and (max-width: 768px) {
    #info-container {
      transform: translateY(14%);
    }
  }
</style>