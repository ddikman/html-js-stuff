<script>
  import { config as slideHamburger } from './slide-hamburger/+page.js';

  const projects = [
    slideHamburger
  ];
</script>

<h1>Lib top page</h1>
<div class="projects">
  {#each projects as project}
    <a class="project-card" href={`/${project.slug}`}>
      <h3>{project.title}</h3>
      <span>{project.description}</span>
    </a>
  {/each}
</div>

<style>
  .projects {
    display: flex;
    flex-wrap: wrap;
  }

  .project-card {
    width: 300px;
    margin: 10px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 1rem;
  }

  .project-card h3 {
    margin: 0;
    margin-bottom: 1rem;
  }
</style>