<script lang="ts">
  // Retrieves the projects
  import projects from "/home/maxence/WebstormProjects/portfolio-website/src/lib/files/projects.json";

  // Retrieves the tag settings
  import tagSettings from "/src/lib/files/tags.json"

  function showProjectDetails() {
    alert("test")
  }
</script>

<div >
  <h1 class="h1 flex flex-col items-center justify-center m-10">My projects</h1>

  <!-- Projects grid -->
  <div class="grid grid-cols-2 gap-2 m-4">
    {#each projects as project}
      <!-- Project card -->
      <div class="card p-4 card-hover" on:click={showProjectDetails}>
        <img src={project.image} alt="{project.title} image" class=""/>
        <h1>
          {project.title}
        </h1>

        <!-- Tags -->
        <div class="">
          {#each project.tags as tag}
            <!-- Warning! The page won't load if a tag isn't set in the tags.json file! -->
            <span class="badge variant-ghost-{tagSettings.find(item => item.name === tag).color}">{tag}</span>
          {/each}
        </div>
        <p>{project.description}</p>
      </div>
    {/each}

  </div>
</div>

