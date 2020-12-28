<script lang="ts">
  import { createEventDispatcher } from "svelte";
  import { NavigationDrawer, Overlay } from "svelte-materialify/src";

  const dispatch = createEventDispatcher();

  export let drawerOpen = false;
  function dispatchDrawer() {
    dispatch("drawer", {});
  }
</script>

<NavigationDrawer absolute active={drawerOpen}>Content</NavigationDrawer>
<Overlay active={drawerOpen} absolute on:click={dispatchDrawer} index={1} />
