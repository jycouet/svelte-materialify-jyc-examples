<script lang="ts">
  import LayoutMenuLink from "./LayoutMenuLink.svelte";
</script>

<style>
  .nav {
    height: 48px;
    border-bottom: 4px solid #007626;
    display: flex;
    align-items: center;
  }

  :global(.nav > a) {
    text-decoration: none;
  }
</style>

<nav class="primary-color">
  <div class="nav">
    <LayoutMenuLink to="/"><span>Home</span></LayoutMenuLink>
    <LayoutMenuLink to="/todos">Todos</LayoutMenuLink>
  </div>
</nav>
