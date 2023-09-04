<script lang="ts">
  import { Modal, getModalStore } from '@skeletonlabs/skeleton';
  import type { ModalSettings, ModalComponent, ModalStore } from '@skeletonlabs/skeleton';

  export let project;

  import tagSettings from "/src/lib/files/tags.json"
  import ProjectModal from "./ProjectModal.svelte";
  import Fa from "svelte-fa";
  import { faUser, faUserGroup } from "@fortawesome/free-solid-svg-icons";

  const modalStore = getModalStore();

  // Displays a custom modal with the project details
  function showProjectDetails() {
    const modalComponent: ModalComponent = {
      ref: ProjectModal,
      props: {project},
    }

    const modal: ModalSettings = {
      type: "component",
      component: modalComponent
    }

    modalStore.trigger(modal)
  }

</script>

<!-- Project card -->
<div class="card p-4 card-hover text-center" on:click={showProjectDetails}>
  <header>
    <img src={project.image} alt="{project.title} image" class="h-40 w-full object-cover rounded-lg" />
  </header>
  <h1 class="h2 m-4">
    {project.title}
  </h1>

  <!-- Tags -->
  <div class="mb-4">
    {#each project.tags as tag}
      <!-- Warning! The page won't load if a tag isn't set in the tags.json file! -->
      <span class="badge variant-{tagSettings.find(item => item.name === tag).color} m-[1px]">{tag}</span>
    {/each}
  </div>

  <!-- Summary -->
  <p class="mb-4">{project.summary}</p>

  <!-- TODO: The footer has to be sticky to the bottom !! -->
  <!-- Footer -->
  <div class="">
    <hr class=""/>
    <footer class="flex items-center mt-4 place-content-between">
      <span class="badge">
        {#if project.type === "Solo"}
          <Fa icon={faUser} />
        {:else}
          <Fa icon={faUserGroup} />
        {/if}
        <span>{project.type}</span>
      </span>
      <span class="badge font-thin">
        {project.startDate}
        <!-- Adds the end date -->
        {#if project.endDate !== null}
          - {project.endDate}
        {/if}
      </span>
    </footer>
  </div>
</div>
