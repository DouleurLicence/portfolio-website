<script lang="ts">
  import { Modal, getModalStore } from '@skeletonlabs/skeleton';
  import type { ModalSettings, ModalComponent, ModalStore } from '@skeletonlabs/skeleton';

  export let project;

  import tagSettings from "/src/lib/files/tags.json"
  import ProjectModal from "./ProjectModal.svelte";

  const modalStore = getModalStore();

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
  <img src={project.image} alt="{project.title} image" class="h-auto max-w-full rounded-lg" />
  <h1>
    {project.title}
  </h1>

  <!-- Tags -->
  <div class="">
    {#each project.tags as tag}
      <!-- Warning! The page won't load if a tag isn't set in the tags.json file! -->
      <span class="badge variant-{tagSettings.find(item => item.name === tag).color} m-[1px]">{tag}</span>
    {/each}
  </div>
  <p>{project.summary}</p>
  <hr/>
  <div class="flex mt-4 place-content-between">
    <span class="badge">{project.type}</span>
    <span class="badge font-thin">{project.startDate} - {project.endDate}</span>
  </div>
</div>
