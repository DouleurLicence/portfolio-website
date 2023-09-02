<script lang="ts">
  // Retrieves the projects
  import projects from "/home/maxence/WebstormProjects/portfolio-website/src/lib/files/projects.json";

  function showProjectDetails() {
    alert("test")
  }
</script>

<h1>This is where the projects go</h1>

<div class="grid grid-cols-2 gap-2 m-4">
  {#each projects as project}
    <div class="card p-4 card-hover" on:click={showProjectDetails}>
      <img src={project.image} alt="{project.title} image" class=""/>
      <h1>
        {project.title}
      </h1>
      <p>{project.description}</p>
    </div>
  {/each}

</div>

