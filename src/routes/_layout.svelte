<script>
  import Nav from "../components/Nav.svelte";
  import { stores } from "@sapper/app";
  const { page } = stores();
  let path = $page.path;
</script>

<style>
  main {
    position: relative;
    max-width: 56em;
    padding: 2em;
    margin: 0 auto;
    box-sizing: border-box;
  }
</style>

<Nav {path} />

<main>
  <slot />
</main>
