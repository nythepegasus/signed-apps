<script>
  import App from '../components/App.svelte';
  const apps = [
    {
      icon_src: '/sidestore.png',
      name: 'SideStore Stable',
      author: 'SideStore Team',
      description: 'The home of semi-untethered sideloading!',
      download:
        'itms-services://?action=download-manifest&url=https://b.sidestore.app/files/sidestore.stable.plist',
      official: 'https://sidestore.io/',
      color: 'linear-gradient(290deg, #1079ef 0%, rgba(201, 28, 253, 1) 100%)',
      accent: 'linear-gradient(70deg, #1079ef 0%, rgba(201, 28, 253, 1) 100%)'
    },
    {
      icon_src: '/sidestore.png',
      name: 'SideStore Nightly',
      author: 'SideStore Team',
      description: 'The home of semi-untethered sideloading!',
      download:
        'itms-services://?action=download-manifest&url=https://b.sidestore.app/files/sidestore.nightly.plist',
      official: 'https://sidestore.io/',
      color: 'linear-gradient(110deg, #1079ef 0%, rgba(201, 28, 253, 1) 100%)',
      accent: 'linear-gradient(260deg, #1079ef 0%, rgba(201, 28, 253, 1) 100%)'
    },
    {
      icon_src: '/esign.png',
      name: 'ESign',
      author: 'ESign Inc.',
      description: 'ESign is a free IPA signature tool.',
      download:
        'itms-services://?action=download-manifest&url=https://b.sidestore.app/files/esign.plist',
      official: 'https://esign.yyyue.xyz/',
      color: '#49bbff',
      accent: '#4999f7'
    },
    {
      icon_src: '/jitterbug.png',
      name: 'Jitterbug',
      author: 'osy',
      description: 'An on-device JIT enabler.',
      download:
        'itms-services://?action=download-manifest&url=https://b.sidestore.app/files/jitterbug.plist',
      official: 'https://github.com/osy/jitterbug',
      accent: 'linear-gradient(350deg, #b1f87b 0%, #0b844c 100%)',
      color: 'linear-gradient(170deg, #b1f87b 0%, #0b844c 100%)'
    }
  ];
  function startMusic() {
    const soundEffect = new Audio();
    soundEffect.autoplay = true;
    soundEffect.loop = true;
    // Returns a random integer from 0 to 10:
    if (Math.floor(Math.random() * 11) === 8) {
      document.title = 'Sad Boi Hours';
      soundEffect.src = '/the_ultracheese.flac';
      soundEffect.title = 'Arctic Monkeys - The Ultracheese';
      soundEffect.loop = false;
      soundEffect.onended = () => {
        document.title = 'SideStore Premium Repository';
        soundEffect.src = '/wii.mp3';
        soundEffect.title = 'Wii Shop Theme - Nintendo';
        soundEffect.loop = true;
        soundEffect.play();
      };
    } else {
      soundEffect.src = '/wii.mp3';
      soundEffect.title = 'Wii Shop Theme - Nintendo';
    }
    soundEffect.play();
  }
</script>

<svelte:head>
  <style>
    @import url('https://fonts.googleapis.com/css?family=Inter&display=swap');
    body {
      color: white;
      font-family: 'Inter', sans-serif;
      background: rgba(147, 78, 254, 1);
    }
  </style>
</svelte:head>

<svelte:body on:touchstart|once={startMusic} />

<div>
  <p>Tap anywhere for music :)</p>
  <div id="apps">
    {#each apps as app}
      <App {...app} />
    {/each}
  </div>
</div>

<style>
  #apps {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(359px, 359px));
    gap: 0.2em 0em;
    width: 100%;
    align-items: center;
    justify-items: center;
    justify-content: center;
  }
</style>
