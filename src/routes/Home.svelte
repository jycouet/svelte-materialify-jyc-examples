<script lang="ts">
  import { Button } from "svelte-materialify/src";
</script>

<style>
  .line {
    display: flex;
    align-items: center;
    height: 50px;
  }
</style>

<br />
<main>
  <div>
    <h2>Home</h2>
    <div class="line">
      Hello
      <Button class="primary-color">button</Button>
      from Home
    </div>
  </div>
</main>
