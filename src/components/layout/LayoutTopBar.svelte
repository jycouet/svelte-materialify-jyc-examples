<script lang="ts">
  import { createEventDispatcher } from "svelte";
  import { AppBar, Button, Icon } from "svelte-materialify/src";

  const dispatch = createEventDispatcher();

  export let theme: "light" | "dark";

  function dispatchTheme() {
    theme = theme === "light" ? "dark" : "light";
    dispatch("theme", { theme });
  }

  function dispatchDrawer() {
    dispatch("drawer", {});
  }
</script>

<AppBar>
  <div slot="icon">
    <Button fab depressed on:click={dispatchDrawer}>
      <Icon class="material-icons">menu</Icon>
    </Button>
  </div>
  <span slot="title"> <span class="font-weight-black">My</span> Demo App </span>
  <div style="flex-grow:1" />
  <Button fab depressed on:click={dispatchTheme}>
    <Icon class="material-icons">
      {theme === 'light' ? 'bedtime' : 'wb_sunny'}
    </Icon>
  </Button>
</AppBar>
