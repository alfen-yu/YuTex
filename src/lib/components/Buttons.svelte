<script lang="ts">
  import { Window } from "@tauri-apps/api/window"
  const appWindow = new Window('theUniqueLabel');

  function minimize() {
    appWindow.minimize();
  }

  function maximize() {
    appWindow.toggleMaximize();
  }

  function close() {
    appWindow.close();
  }
</script>

<header class="titlebar">
  <div class="title">YuTex</div>
  <div class="window-controls">
    <button on:click={minimize}>−</button>
    <button on:click={maximize}>□</button>
    <button on:click={close}>×</button>
  </div>
</header>

<style>
  .titlebar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #1e1e1e;
    color: white;
    padding: 0.25rem 1rem;
    height: 30px;
    user-select: none;
    -webkit-app-region: drag; /* allows dragging the window */
  }

  .window-controls {
    display: flex;
    gap: 0.5rem;
    -webkit-app-region: no-drag; /* make buttons clickable */
  }

  .window-controls button {
    background: transparent;
    color: white;
    border: none;
    cursor: pointer;
    width: 28px;
    height: 24px;
    border-radius: 4px;
  }

  .window-controls button:hover {
    background: #333;
  }

  .window-controls button:last-child:hover {
    background: #c42b1c;
  }
</style>
