<script lang="ts">
  import { onMount } from 'svelte'
  import Loader from '$src/components/Loader.svelte';
  import Logo from '$src/components/Logo.svelte'
  import Countdown from '$src/components/Countdown.svelte';
  import Footer from '$src/components/Footer.svelte';

  onMount(async () => {
    const { Model } = await import('$src/threejs/homepage')
    new Model({
      dom: 'homecity',
      model: '/homepage/MainMenu_Stripes_animated.glb?020620220002',
      hdr: '/homepage/venice_sunset_1k.hdr?020620220002',
    })
  })
</script>

<style>
  .home {
    background: #000 ;
    overflow: hidden; 
    height: 100vh;
    width: 100vw; 
  }
  .home-inner {
    height: 100vh;
    width: 101vw; 
    position: relative;
    margin: 0 auto; 
  }
  .layer {
    color: #fff;
    position: absolute;
  }
</style>

<div class="home">
  <div class="home-inner">
    <div class="layer" style="top: 0%; width: 100%; height: 100vh;">
      <div id="homecity" style="position: absolute; left: 0; top: 0; width: 100%; height: 100%;"></div>
    </div>
  </div>

  <Loader />
  <Countdown />
  <Logo />
  <Footer />
</div>