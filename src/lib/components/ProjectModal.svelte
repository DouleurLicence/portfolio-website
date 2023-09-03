<script lang="ts">
  import Fa from "svelte-fa";
  import { faRightFromBracket } from "@fortawesome/free-solid-svg-icons";

  export let project;
</script>

<div class="">
  <h1 class="h1 mb-8">{project.title}</h1>

  <p>{project.longDescription}</p>

  {#if project.githubLink !== null}
    <a href="{project.githubLink}" class="anchor flex items-center justify-center mt-4">
      Project link
      <Fa icon={faRightFromBracket} class="ml-1"/>
    </a>
  {/if}
</div>