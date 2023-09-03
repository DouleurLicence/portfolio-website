<script>
  import { page } from '$app/stores';

  import Fa from "svelte-fa";
  import {faWarning} from "@fortawesome/free-solid-svg-icons";
  import {faArrowRight} from "@fortawesome/free-solid-svg-icons";
</script>

<div class="flex flex-col items-center justify-center h-full">

  <h1 class="mb-10 h1">Oops! An error occurred!</h1>

  <aside class="alert variant-ghost-error">
    <!-- Icon -->
    <Fa icon={faWarning} size="2x"/>
    <!-- Message -->
    <div class="alert-message flex flex-col items-center justify-center">
      <p class="h3">Error {$page.status}</p>
      <p>{$page.error.message}</p>
    </div>
    <!-- Actions -->
    <div class="alert-actions">
      <a href="/" class="btn variant-filled-tertiary">
        Go back to SafeLand
        <Fa icon={faArrowRight} class="ml-2" />
      </a>
    </div>
  </aside>
</div>