<script>
	import App from '../components/App.svelte';
	const apps = [{
		icon_src: "/sidestore.png",
		name: "SideStore",
		author: "SideStore Team",
		description: "The home of jailed semi-untethered sideloading! This is the stable version.",
		download: "itms-services://?action=download-manifest&url=https://b.sidestore.app/files/sidestore.stable.plist",
		official: "https://sidestore.io/"
	},
	{
		icon_src: "/sidestore.png",
		name: "SideStore Nightly",
		author: "SideStore Team",
		description: "The home of jailed semi-untethered sideloading! This is the nightly version.",
		download: "itms-services://?action=download-manifest&url=https://b.sidestore.app/files/sidestore.nightly.plist",
		official: "https://sidestore.io/"
	},
	{
		icon_src: "/esign.png",
		name: "ESign",
		author: "ESign Inc.",
		description: "ESign is a free IPA signature tool.",
		download: "itms-services://?action=download-manifest&url=https://b.sidestore.app/files/esign.plist",
		official: "https://esign.yyyue.xyz/"
	},
	{
		icon_src: "/jitterbug.png",
		name: "Jitterbug",
		author: "osy",
		description: "An on-device JIT enabler.",
		download: "itms-services://?action=download-manifest&url=https://b.sidestore.app/files/jitterbug.plist",
		official: "https://github.com/osy/jitterbug"
	}]
	function startMusic(){
		const soundEffect = new Audio();
		soundEffect.autoplay = true;
		soundEffect.src = "https://b.sidestore.app/wii.mp3";
		soundEffect.title = "Wii Shop Theme - SideStore Premium";
		soundEffect.play();
	}

</script>
<div on:touchstart|once={startMusic}>
	<p>Tap me for music :)</p>
	<div id="apps">
		{#each apps as app}
			<App {...app} />
		{/each}
	</div>
</div>

<style>
#apps {
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(22.4em, 1fr));
	gap: 0.2em 0.3em;
	align-items: center;
	justify-content: center;
	width: 100%;
}
</style>
