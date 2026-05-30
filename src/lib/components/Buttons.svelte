<script lang="ts">
  import { getCurrentWindow } from "@tauri-apps/api/window";

  const appWindow = getCurrentWindow();

  async function minimize() {
    await appWindow.minimize();
  }

  async function maximize() {
    await appWindow.toggleMaximize();
  }

  async function close() {
    await appWindow.close();
  }
</script>

<header class="titlebar">
  <div class="window-controls">
    <button class="control minimize" type="button" aria-label="Minimize" on:click={minimize}></button>
    <button class="control maximize" type="button" aria-label="Maximize" on:click={maximize}></button>
    <button class="control close" type="button" aria-label="Close" on:click={close}></button>
  </div>
</header>

<style>
  .titlebar {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    width: 100%;
    height: 100%;
    user-select: none;
    -webkit-app-region: drag;
  }

  .window-controls {
    display: flex;
    height: 100%;
    -webkit-app-region: no-drag;
  }

  .control {
    position: relative;
    width: 46px;
    height: 100%;
    background: transparent;
    border: none;
    cursor: pointer;
    color: #cccccc;
  }

  .control:hover {
    background: rgba(255, 255, 255, 0.08);
  }

  .control.close:hover {
    background: #e81123;
    color: #ffffff;
  }

  .minimize::before,
  .maximize::before,
  .close::before,
  .close::after {
    content: "";
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    background: currentColor;
  }

  .minimize::before {
    width: 12px;
    height: 1px;
    top: calc(50% + 3px);
  }

  .maximize::before {
    width: 11px;
    height: 11px;
    background: transparent;
    border: 1.5px solid currentColor;
    box-sizing: border-box;
  }

  .close::before,
  .close::after {
    width: 12px;
    height: 1.5px;
  }

  .close::before {
    transform: translate(-50%, -50%) rotate(45deg);
  }

  .close::after {
    transform: translate(-50%, -50%) rotate(-45deg);
  }
</style>
