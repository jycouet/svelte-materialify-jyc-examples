<script>
  import { Link } from "svelte-routing";

  export let to = "";

  let active = false;
  function getProps({ location, href, isPartiallyCurrent, isCurrent }) {
    active = href === "/" ? isCurrent : isPartiallyCurrent || isCurrent;
  }
</script>

<style>
  .link {
    color: white;
    text-transform: uppercase;
    margin-left: 24px;
    margin-right: 24px;
    text-decoration: none;
  }
  .link:hover {
    border-bottom: 4px solid #fff;
    padding-bottom: 11px;
  }
  .active {
    border-bottom: 4px solid #fff;
    padding-bottom: 11px;
  }
</style>

<Link {to} {getProps} style="color: red">
  <span class="link" class:active>
    <slot />
  </span>
</Link>
