<script>
	export let icon_src;
	export let name;
	export let author;
	export let description;
	export let download;
	export let official;
</script>

<div id="app">
	<img id="icon" src="{icon_src}" alt="{name} icon" />
	<div id="name">{name}</div>
	<div id="author">{author}</div>
	<div id="description">{description}</div>
	<button id="download" on:click={ () => {window.open(download, '_blank'); return false; } }>Download</button>
	<button id="official" on:click={ () => {window.open(official, '_blank'); return false; } }>Official Page</button>
</div> 

<style>
#app {
  display: grid;
	grid-template-columns: 10em 12em;
	gap: 0.2em 0.8em;
	margin: 0.1em 0em;
	padding: 0.1em 0em;
}
#icon {
	border-radius: 25px;
	height: 10em;
  width: 10em;
	grid-column: 1;
	grid-row: 1 / 5;
}
#name {
  grid-column: 2;
	grid-row: 1;
	font-size: 1.3em;
}
#author {
	grid-column: 2;
	grid-row: 2;
}
#description {
	grid-column: 2;
	grid-row: 3;
}
#download {
	grid-column: 1;
	grid-row: 5;
	font-size: 1.1em;
}
#official {
	grid-column: 2;
	grid-row: 5;
	font-size: 1.1em;
}
</style>
