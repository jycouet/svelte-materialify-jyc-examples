<script lang="ts">
  import { Container, MaterialApp } from "svelte-materialify/src";
  import { Route, Router } from "svelte-routing";
  import LayoutDrawer from "./components/layout/LayoutDrawer.svelte";
  import LayoutMenu from "./components/layout/LayoutMenu.svelte";
  import LayoutTopBar from "./components/layout/LayoutTopBar.svelte";
  import Home from "./routes/Home.svelte";
  import Todos from "./routes/Todos.svelte";

  let theme: "light" | "dark" = "dark";
  function handleTheme(event) {
    theme = event.detail.theme;
  }

  let drawerOpen: boolean = false;
  function handleDrawer() {
    drawerOpen = !drawerOpen;
  }

  export let url = "";
</script>

<style>
  :global(.s-app) {
    height: 100%;
  }
</style>

<MaterialApp {theme}>
  <LayoutDrawer {drawerOpen} on:drawer={handleDrawer} />
  <LayoutTopBar {theme} on:theme={handleTheme} on:drawer={handleDrawer} />

  <Router {url}>
    <LayoutMenu />
    <Container>
      <Route path="">
        <Home />
      </Route>
      <Route path="todos">
        <Todos />
      </Route>
    </Container>
  </Router>
</MaterialApp>
