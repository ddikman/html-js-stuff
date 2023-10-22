<script>
  import Menu from './menu.svelte';
  import { config } from './+page.js';
</script>

<Menu />

<main>
  <h1>{config.title}</h1>
  <p>{config.description}</p>
  <a href="/">Return to top</a>
</main>