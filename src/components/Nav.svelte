<script>
  export let path;
  import { primary, secondary } from "../styleguide/colors.js";
  import data from "../mock.js";
</script>

<style>
  nav {
    border-bottom: 1px solid var(--secondary);
    font-weight: 300;
    padding: 0 1em;
  }

  ul {
    margin: 0;
    padding: 0;
  }

  /* clearfix */
  ul::after {
    content: "";
    display: block;
    clear: both;
  }

  li {
    display: block;
    float: left;
  }

  .selected {
    position: relative;
    display: inline-block;
  }

  .selected::after {
    position: absolute;
    content: "";
    width: calc(100% - 1em);
    height: 2px;
    background-color: #52b3d9;
    display: block;
    bottom: -1px;
  }

  a {
    text-decoration: none;
    padding: 1em 0.5em;
    display: block;
  }
</style>

<nav style="--secondary:{secondary}; --primary:{primary}">
  {#each data.menu as menu}
    <ul>
      <li>
        <a
          rel="prefetch"
          class={path === menu.url ? 'selected' : ''}
          href={menu.url}>
          {menu.portuguese.title}
        </a>
      </li>
    </ul>
  {/each}
</nav>
