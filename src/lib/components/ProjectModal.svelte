<script lang="ts">
  export let project;
</script>

<div>
  <h1 class="h1">{project.title}</h1>

  <p>{project.longDescription}</p>

  {#if project.githubLink !== null}
    Project link: {project.githubLink}
  {/if}
</div>