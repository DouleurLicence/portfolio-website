<script lang="ts">
  // Retrieves the projects
  import projects from "/home/maxence/WebstormProjects/portfolio-website/src/lib/files/projects.json";

  const schoolProjects = projects.filter((project) => project.scholar === true);
  const personalProjects = projects.filter((project) => project.scholar === false);

  // Retrieves the tag settings
  import ProjectCard from "../../lib/components/ProjectCard.svelte";

</script>

<div >
  <h1 class="h1 flex flex-col items-center justify-center m-10">My projects</h1>

  <!-- TODO: Create a grid for cards component -->

  <!-- School Projects grid -->
  <hr />
  <h2 class="h2 m-4" >School projects</h2>
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-2 m-4">
    {#each schoolProjects as project}
      <ProjectCard project={project} />
    {/each}
  </div>

  <!-- Personal Projects grid -->
  <hr />
  <h2 class="h2 m-4" >Personal projects</h2>
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-2 m-4">
    {#each personalProjects as project}
      <ProjectCard project={project} />
    {/each}
  </div>
</div>

