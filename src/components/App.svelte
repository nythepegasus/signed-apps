<script>
  export let icon_src;
  export let name;
  export let author;
  export let description;
  export let download;
  export let official;
  export let color;
  export let accent;
</script>

<div id="app" style="background: {accent}">
  <img id="icon" src={icon_src} alt="{name} icon" />
  <div id="name">{name}</div>
  <div id="author">{author}</div>
  <div id="description">{description}</div>
  <button
    id="download"
    style="background: {color}"
    on:click={() => {
      window.open(download, '_blank');
      return false;
    }}>Download</button
  >
  <button
    id="official"
    style="background: {color}"
    on:click={() => {
      window.open(official, '_blank');
      return false;
    }}>Official Page</button
  >
</div>

<style>
  #app {
    display: grid;
    grid-template-columns: 150px 12em;
    gap: 0.2em 0.8em;
    padding-top: 0em;
    padding-left: -2px;
    padding-bottom: 0.4em;
    justify-content: center;
    border-radius: 25px;
    color: white;
  }
  #icon {
    grid-row: 1 / 5;
    border-radius: 25px;
    height: 150px;
    width: 150px;
  }
  #name {
    grid-row: 1;
    font-size: 1.3em;
  }
  #author {
    grid-row: 2;
  }
  #description {
    grid-row: 3;
  }
  #icon,
  #download {
    grid-column: 1;
  }
  #name,
  #author,
  #description,
  #official {
    grid-column: 2;
  }
  #download,
  #official {
    grid-row: 5;
    margin: auto;
    width: fit-content;
    font-size: 1.1em;
    padding: 0.225em 0.5em;
    border: none;
    border-radius: 10px;
    color: white;
  }
</style>
