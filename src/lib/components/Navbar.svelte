<script lang="ts">
  import Buttons from "$lib/components/Buttons.svelte";
</script>

<header class="navbar">
  <div class="navbar-left">
    <span class="logo">YuTex</span>
  </div>

  <div class="navbar-center">
    <!-- future compile or menu buttons can go here -->
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
    background: #1e1e1e;
    color: #fff;
    padding: 0 1rem;
    height: 32px;
    -webkit-app-region: drag;
  }

  .navbar-right {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    -webkit-app-region: no-drag;
  }

  .logo {
    font-weight: 600;
    letter-spacing: 0.5px;
  }
</style>
