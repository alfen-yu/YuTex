<script lang="ts">
  import Navbar from "$lib/components/Navbar.svelte";
  import Sidebar from "$lib/components/Sidebar.svelte";
  import Editor from "$lib/components/Editor.svelte";
  import Viewer from "$lib/components/Viewer.svelte";
  import Dock from "$lib/components/Dock.svelte";
</script>

<main class="container">
  <div class="row-1">
    <Navbar />
  </div>
  <div class="row-2">
    <Sidebar />
    <Editor />
    <Viewer />
  </div>
  <div class="row-3">
    <Dock />
  </div>
</main>

<style>
  :global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  :root {
    color: #f6f6f6;
    background-color: #2f2f2f;
    font-family: Inter, Avenir, Helvetica, Arial, sans-serif;
    font-synthesis: none;
    text-rendering: optimizeLegibility;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    -webkit-text-size-adjust: 100%;
  }

  .container {
    display: grid;
    grid-template-rows: auto 1fr auto;
    height: 100vh;
  }

  .row-2 {
    display: grid;
    /* sidebar | editor | viewer */
    grid-template-columns: 1fr 2fr 1fr;
    gap: 4px;
    height: 100%;
  }

  .row-1,
  .row-3 {
    background-color: #1e1e1e;
    text-align: center;
  }

  div {
    border: 1px solid red;
  }
</style>
