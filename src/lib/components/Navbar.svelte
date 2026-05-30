<script lang="ts">
  import Buttons from "$lib/components/Buttons.svelte";
</script>

<header class="navbar">
  <div class="navbar-left">
    <span class="logo">YuTex</span>
    <div class="nav-dropdowns">
      <p>File</p>
      <p>Edit</p>
    </div>
  </div>

  <div class="navbar-right">
    <Buttons />
  </div>
</header>

<style>
  .navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #2d2d2d;
    color: #d4d4d4;
    padding: 0 0 0 1rem;
    height: 32px;
    -webkit-app-region: drag;
    border-bottom: 1px solid #1b1b1b;
  }

  .navbar-left {
    display: flex;
    align-items: center;
    gap: 1rem;
    min-width: 0;
  }

  .navbar-right {
    display: flex;
    align-items: center;
    height: 100%;
    -webkit-app-region: no-drag;
  }

  .logo {
    font-weight: 600;
    letter-spacing: 0.5px;
  }

  .nav-dropdowns {
    display: flex;
    align-items: center;
    gap: 0.9rem;
    font-size: 0.875rem;
  }

  .nav-dropdowns p {
    opacity: 0.92;
  }
</style>
